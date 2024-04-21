- Pag 125
1) Fai delle Virtual lan
2) Configura Trunk se collegato con switch/router
3) POI SUL ROUTER scrivere:
- enable
- config t
- Interface (Interfaccia es Gig0/0) e metti il .20 (20 sarebbe la VLAN)
- ip address (indirizzo.254) (subnet)
- encapsulation dot1q 20
- exit