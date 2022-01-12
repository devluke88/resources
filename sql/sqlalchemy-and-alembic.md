# SQLAlchemy and Alembic

### DB migrations using Alembic

```
# 1. install alembic - time of writing current version used - alembic 1.7.5 

pip install alembic

# 2. Inititiate alembic
alembic init alembic

# 3. Update alemnic.ini file with db connection details, for example:
sqlalchemy.url = mysql+pymysql://root:admin1234@127.0.0.1:3306/service_dashboard

# 4. Edit alembic/env.py and add the following:
from models import Base
target_metadata = Base.metadata
# save your file

#5. For existing db generate first migration and add your stuff, so create migration manually, by running:
alembic revision -m "First migration"

# 6. After above commend yuo will have a new versioned fiele in versions directory, for example: bf35c09ac2e3
# edit file and add your changes, for example we want to add new columns:

def upgrade():
    op.add_column('test_table', sa.Column('column_name', sa.String(255)))


def downgrade():
    op.drop_column('test_table', 'column_name')
    
# 7. Run migrations with command: 
alembic upgrade head

# For future you will generate new migrations with automatic migrations:
alembic revision --autogenerate -m "Add new columns"
```
