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

2.2












