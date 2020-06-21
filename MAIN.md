# Main

Se ahace el curso sobre "BDD, Behat, Mink and other Wonderful Things"

## Instalar driver para FIREFOX

- Geckodriver revisar que version de firefox tenes instalada. 
    version 75.0 64-bit

    wget https://github.com/mozilla/geckodriver/releases/download/v0.26.0/geckodriver-v0.26.0-linux64.tar.gz
    sudo sh -c 'tar -x geckodriver -zf geckodriver-v0.26.0-linux64.tar.gz -O > /usr/bin/geckodriver'
    sudo chmod +x /usr/bin/geckodriver
    rm geckodriver-v0.26.0-linux64.tar.gz
    geckodriver --version

## Instalar driver para CHROME
- chrome driver revisar que version de crome tenes instalada. 
    version 81.0.4044.138 (Official Build) (64-bit)

    wget https://chromedriver.storage.googleapis.com/81.0.4044.138/chromedriver_linux64.zip
    unzip unzip chromedriver_linux64.zip 
    sudo mv chromedriver /usr/bin/chromedriver
    sudo chmod +x /usr/bin/chromedriver
    rm chromedriver_linux64.zip
    chromedriver --version


# Capitulo 00 - install

## link 
- https://symfonycasts.com/screencast/behat/install
- https://github.com/knpuniversity/behat


## Pasos

    Bajar el proyecto desde "https://github.com/knpuniversity/behat"
    descomprimir e instalar todo 
        composer install

    Cargar la base de datos sqlite "app/app.db"
        php app/console doctrine:database:create
        php app/console doctrine:schema:update --force
        php app/console doctrine:fixtures:load

    Encender servidor
        php app/console server:run


    Entra a la url http://localhost:8000.

    Te podes logear con:
        - user: admin
        - pass: admin

# Capitulo 01 - From Install to JS Testing

## link 
- https://symfonycasts.com/screencast/behat/install

## Pasos

    Usando gotte 
        $ composer require behat/mink-extension behat/mink-goutte-driver
        $ vendor/bin/behat
        $ vendor/bin/behat --init
        $ ./vendor/bin/behat

    Usando selenium 
        
        $ composer require behat/mink-selenium2-driver

    Los standalone estan aca http://selenium-release.storage.googleapis.com/index.html

        $ wget http://selenium-release.storage.googleapis.com/3.7/selenium-server-standalone-3.7.1.jar
        $ wget http://selenium-release.storage.googleapis.com/3.9/selenium-server-standalone-3.9.1.jar

    Encender servidor de selenium 

        $ clear; java -jar download/selenium-server-standalone-3.9.1.jar 

    Agregar a behat.yml al selenium

        $ ./vendor/bin/behat


## PRUEBA
    Levantar el servidor de LAMP
        php app/console server:run

    Activar selenium standalone
        clear; java -jar download/selenium-server-standalone-3.9.1.jar 

    Ejecutar behat 
        ./vendor/bin/behat

# Capitulo 02 - BDD Features [https://symfonycasts.com/screencast/behat/bdd-features]

Crear una nuevas STORY :
    - authentication
    - fence api
    - product admin