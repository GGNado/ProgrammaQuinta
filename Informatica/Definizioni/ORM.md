## Cos'è ORM
- Serve per semplificare il lavoro
- Qualsiasi sia il db che utilizziamo dobbiamo scrivere sempre le stesse cose
-  Python [[SqlAlchemy]]
- [[JPA]] per Java
- Tecnica che ci permette di programmare su un linguaggio, e le modifiche avvengono sul DB.

## Pratica
1) database.py
```python
from sqlalchemy.orm import declarative_base, sessionmaker
from sqlalchemy import create_engine

engine = create_engine(
	'sqlite:///./PeopleDB.db', #"mysql://nomeutente:password@localhost/nomeDB
	echo = True
)

Base = declarative_base()
SessionLocal = sessionmaker(bind = engine)
```
2) PersonModel.py
```python
from db.database import Base
from sqlalchemy import Column, Integer, String

class PersonModel(Base):
	__tablename__ = 'People'
	id = Column(Integer, primary_key = True)
	firstname = Column(String(48), nullable = False)
	lastname = Column(String(48), nullable = False)
	age = Column(Integer, nullable = False)
```
3) PersonRouter.py
```python
from sqlalchemy import exc
from entity.Person import Person
from db.database import SessionLocal
from models.PersonModel import PersonModel
from fastapi import APIRouter, HTTPException

router = APIRouter(
	tags = ['Person'],
	prefix = '/api/person'
)

session = SessionLocal()

@router.post('/')
async def createPerson(person: Person):
	session.add(
		PersonModel(
			id = person.id,
			firstname = person.firstname.strip(),
			lastname = person.lastname.strip(),
			age = person.age
		)
	)
	try:
		session.commit()
	except exc.SQLAlchemyError:
		session.rollback()
		raise HTTPException(detail = 'Unable to add new Person! Maybe same ID already exists!', status_code = 404)
	return 'Success! A new person has been added to the list!'

@router.get('/')
async def getPeople():
	return session.query(PersonModel).all()

@router.get('/{id}')
async def getPerson(id: int):
	p = session.query(PersonModel).filter(PersonModel.id == id).first()
	if p:
		return p
	raise HTTPException(detail = f'ID Person {id} not found!..', status_code = 404)

@router.put('/{id}')
async def modifyPerson(id: int, person: Person):
	try:
		session.query(PersonModel).filter(PersonModel.id == id).update({
			'firstname': person.firstname.strip(),
			'lastname': person.lastname.strip(),
			'age': person.age
		})
		session.commit()
	except exc.SQLAlchemyError:
		session.rollback()
		raise HTTPException(detail = f'Error! Unable remove Person id {id}', status_code = 404)
	return f'Person with ID {id} updated successfully'

@router.delete('/{id}')
async def removePerson(id: int):
	try:
		p = session.query(PersonModel).filter(PersonModel.id == id).delete()
		session.commit()
		if p:
			return f'Success! Correct remove Person ID {id}!'
		else:
			session.rollback()
			raise HTTPException(detail = f'Error! Unable remove Person id {id}', status_code = 404)
	except exc.SQLAlchemyError:
		session.rollback()
		raise HTTPException(detail = f'Error! Unable remove Person id {id}', status_code = 404)
```
