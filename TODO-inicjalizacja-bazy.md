#Inicjalizacja postgres w dockerze 

	Baza bookee z tabelą book.
	Dla 1 i 2 używamy init_postgres_db_and_user.sql
	Dla 3 i 4 używamy init_postgres_db_and_user_hibernate

##1. Zainstalowanie Docker


##2. Kontener z bazą postgres
	docker run -d --name postgress_with_bookee -p 5432:5432 -e POSTGRES_PASSWORD=my_pass postgres

##3. Skopiowanie pliku do kontenera
	docker cp ./init_postgres_db_and_user.sql postgress_with_bookee:/opt/init_postgres_db_and_user.sql
		docker cp ./init_postgres_db_and_user.sql postgress_with_bookee:/opt/init_postgres_db_and_user_hibernate.sql


##4. Uruchomienie skryptu w kontenerze
	docker exec postgress_with_bookee psql -U postgres -f /opt/init_postgres_db_and_user.sql
		docker exec postgress_with_bookee2 psql -U postgres -f /opt/init_postgres_db_and_user_hibernate.sql

// winpty docker exec -it postgress_with_bookee bash?

cd opt
ls
docker exec postgress_with_bookee psql -U postgres -f /opt/init_postgres_db_and_user.sql
psql -U postgres -f ./init_postgres_db_and_user.sql ( lub _hibernate)
/ docker pull postgres
/ -p - open ports
/ -d - detached instance of program(work in background)
/ -e - sending environemnt variable










##2. Kontener z bazą postgres
	docker run -d --name postgress_with_bookee5 -p 5435:5435 -e POSTGRES_PASSWORD=my_pass postgres

##3. Skopiowanie pliku do kontenera
	docker cp ./init_postgres_db_and_user_hibernate.sql postgress_with_bookee5:/opt/init_postgres_db_and_user_hibernate.sql
	


##4. Uruchomienie skryptu w kontenerze
	docker exec postgress_with_bookee5 psql -U postgres -f /opt/init_postgres_db_and_user_hibernate.sql

// winpty docker exec -it postgress_with_bookee bash?

cd opt
ls
docker exec postgress_with_bookee psql -U postgres -f /opt/init_postgres_db_and_user.sql
psql -U psotgres -f ./init_postgres_db_and_user.sql