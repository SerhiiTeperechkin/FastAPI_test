ALEMBIC = alembic

PHONY: mm m

mm: # make migration
	${ALEMBIC} revision --autogenerate -m ${msg}

m: # migrate
	${ALEMBIC} upgrade head

