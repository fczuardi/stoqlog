Python 2 virtualenv, without stoq PYTHONPATH

- checkout das dependencias nos commits corretos:
  - kiwi 1.11.1
  - stoqdrivers 1.4.2 (1.3.3) (comenta a kiwi do requirements.txt)
  - stoq 2.1 (comenta weasyprint, kiwi, poppler do requirements.txt)
  - storm (fork da stoq)
- para cada uma delas entrar no diretório e dar `python setup.py install`
- psycopg2 normal da distro
- adicionar na tabela system_user o email do google e is_admin 't'
- apistoq/localconfig.py

    SERVER_NAME = 'localhost:5000'
    DB_USER = 'fcz'
    DEBUG = True

- acessar http://localhost:5000

