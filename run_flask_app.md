## Hello!

# To Run the Flask app:

### First of all ensure that postgresql is downloaded (if this part is ensured, skip to the flask app):
> psql -V

### if not downloaded:

"""
sudo apt install curl ca-certificates
sudo install -d /usr/share/postgresql-common/pgdg
sudo curl -o /usr/share/postgresql-common/pgdg/apt.postgresql.org.asc --fail https://www.postgresql.org/media/keys/ACCC4CF8.asc
sudo sh -c 'echo "deb [signed-by=/usr/share/postgresql-common/pgdg/apt.postgresql.org.asc] https://apt.postgresql.org/pub/repos/apt $(lsb_release -cs)-pgdg main" > /etc/apt/sources.list.d/pgdg.list'
sudo apt update
sudo apt -y install postgresql
"""

### then follow the following steps one by one:

> sudo -i -u postgres
> psql
> CREATE USER <username> WITH PASSWORD '<password>';
> CREATE DATABASE <db_name> WITH OWNER <username>;
> GRANT ALL PRIVILEGES ON DATABASE <db_name> TO <username>;
> \q

### Now, to connect to the database using the user we just created:
( no need to be in the postgres user )

> psql -h 127.0.0.1 -U <username> -d <db_name>

you will be prompted to enter the password. Enter it, and enter all SQL commands you want...

## Keep the postrgresql Terminal Tab Open

# Flask App:
You will need to download all requirements:
go to ../src/ and open a terminal there. 
Find the requirements.txt file that has all required libraries.
### Download them using:

> pip install -r requirements.txt

## Now, you can run the views.py file:

> python views.py

Navigate to the logged IPv4 address in your browser to check the website out. 
Begin by Creating a team, then adding an experiment to that team.

You can move on to add new CSV file like this one:

ID,Source,Geolocation,Location,State,Sightning date,Post date,Abund,Size,Ecological relation/Other strandings,Human interaction/Accident,Age,Sex,Site,URL 1,URL 2,URL 3,URL 4,URL 5
1,SM,,Peruíbee,SP,,6/19/2013,,,,,,,,https://www.instagram.com/p/paSlHTv-IT_/,,,,
2,SM,,"Piruie, Arembepe, Bahia",BA,,7/10/2013,,,Scavenging by insects by ari,,,,,https://www.instagram.com/p/bMruL_Qmvh/,,,,
3,SM,"Barra De São Miguele, Al",,AL,,1/28/2014,,,,,,,,https://www.instagram.com/p/ju0YFlAVY3/,,,,

Finally, you can view all the data in the database in the query tables tab
