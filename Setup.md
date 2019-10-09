## Setup

1. `sudo apt install git python3 python3-pip python3-venv postgresql libpq-dev`
2. `git clone https://github.com/jjiege/odoo.git`
3. `python3 -m venv odoo-dev`
4. `source odoo-dev/bin/activate`
5. `pip3 install -r requirements.txt`
6. `sudo service postgresql start`
7. `sudo su - postgres`
8. `createuser --createdb --username postgres --no-createrole --no-superuser --pwprompt odoo`
9. `sudo nano /etc/postgresql/11/main/pg_hba.conf`
    - local    all    odoo    trust
10. `sudo service postgresql restart`
11. `sudo nano odoo.conf`
    - [options]
    ; This is the password that allows database operations:
    ; admin_passwd =
    db_host = False
    db_port = False
    db_user = odoo
    db_password =
    addons_path = addons, odoo/addons
12. `./odoo-bin -c odoo.conf`
13. [localhost:8069](http://localhost:8069)