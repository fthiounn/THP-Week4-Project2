2. Le projet
2.1. La startup tech du moment
	- Dans le fichier startup_tech.sqlite il y a les 4 tables demandées +1 table représentant la relation many to many de article et category
		- Table User : 				id 	integer (primary key)
									name text
		- Table Article:			id integer (primary key)
									name text
									id_user (foreign key from User) - relation One user for Many article
		- Table Category 			id integer (primary key)
									titre text
		- Table Category_article	id_article (foreign key from Article)
									id_category (foreign key from Category)
									Relation Many Article to Many Category
		- Table Tag					id integer (primary key)
									titre text
									couleur text
									id_category (foreign key from Category) - relation One Category for Many tags

2.2. Concepts de sites et base de donnée
2.2.1. MOOCcademy

	- Table Course : 				id integer (primary key)
									title text
									description text
	- Table Lesson : 				id integer (primary key)
									title text
									body text
									id_course (foreign key from Course) - relation One Course for Many Lessons

2.2.2. The Hacking Pinterest

	- Table User					id integer (primary key)
									name text
	- Table Pins					id integer (primary key)
									url text
									id_user (foreign key from User) - relation One User for Many Pins
	- Table Comment					id integer (primary key)
									content text
									id_user (foreign key from User) - relation One User for Many Comment
									id_pins (foreign key from Pins) - relation One Pins for Many Comment

2.2.3 The Hacking News
	
	- Table User					id integer (primary key)
									name text
	- Table Link					id integer (primary key)
									url text
									id_user (foreign key from User) - relation One User for Many Link
	- Table Comment					id integer (primary key)
									content text
									id_user (foreign key from User) - relation One User for Many Comment
									id_link (foreign key from Link) - relation One Link for Many Comment
	- Table Commentofcomment		id integer (primary key)
									content text
									id_comment (foreign key from comment) - relation One Comment for Many Commentofcomment

2.2.4 The Hacking Class

	- Table Student					id integer (primary key)
									name text
									id_class (foreign key from Class) - relation One Class for Many Students
	- Table Class					id integer (primary key)
									content text

2.3 Faire des requetes en base

- Récupérer tous les albums
	=> SELECT * FROM albums;

- Récupérer tous les albums dont le titre contient "Great"
	=> SELECT * FROM albums WHERE Title LIKE '%Great%';

- Donner le nombre total d'albums contenus dans la base
	=> SELECT COUNT( * ) FROM albums;

- Supprimer tous les albums dont le nom contient "music"
	=> DELETE FROM albums WHERE Title LIKE '%music%';

- Récupérer tous les albums écrits par AC/DC
	=> SELECT * FROM albums A WHERE A.ArtistId IN ( SELECT B.ArtistId FROM artists B WHERE B.Name='AC/DC'); 

- Récupérer tous les titres des albums de AC/DC
	=> SELECT A.Title FROM albums A WHERE A.ArtistId IN ( SELECT B.ArtistId FROM artists B WHERE B.Name='AC/DC');

- Récupérer la liste des titres de l'album "Let There Be Rock"
	=> SELECT A.Name FROM tracks A WHERE A.AlbumId IN ( SELECT B.AlbumId FROM albums B WHERE B.Title='Let There Be Rock');

- Afficher le prix de cet album ainsi que sa durée totale
	=> SELECT SUM (UnitPrice) AS AlbumPriceAndDuration FROM tracks A WHERE A.AlbumId IN (SELECT B.AlbumId FROM albums B WHERE B.Title='Let There Be Rock') 
	UNION
	SELECT SUM (Milliseconds) FROM tracks A WHERE A.AlbumId IN (SELECT B.AlbumId FROM albums B WHERE B.Title='Let There Be Rock');

- Afficher le coût de l'intégralité de la discographie de "Deep Purple"
	=> SELECT SUM (UnitPrice) AS DeepPurpleDiscoPrice FROM tracks A WHERE A.AlbumId IN (SELECT B.AlbumId FROM albums B WHERE B.ArtistId IN ( SELECT C.ArtistId FROM artists C WHERE C.Name='Deep Purple'));

- Créer l'album de ton artiste favori en base, en renseignant correctement les trois tables albums, artists et tracks

DATA: 
	Table tracks : TrackId(key), Name, AlbumId(foreign key), MediaTypeId, GenreId, Composer, Milliseconds, Bytes, UnitPrice
	Table 


Daft Punk - Discovery
name				
1.	One More Time								5:20
2.	Aerodynamic									3:27
3.	Digital Love (featuring DJ Sneak)			4:58
4.	Harder, Better, Faster, Stronger			3:43
5.	Crescendolls								3:28
6.	Nightvision									1:43
7.	Superheroes									3:57
8.	High Life									3:13
9.	Something About Us							3:50
10.	Voyager										3:46
11.	Veridis Quo									5:44
12.	Short Circuit								3:24
13.	Face to Face								3:58
14.	Too Long									10:00






