Erklärung der Projektstruktur:
*composer.json / und lock für Abhängigkeiten
*Docker und Vagrant-File für Deployment auf diese Umgebeung
*config-Ordner für Konfiguration
*data-Ordner für autom. durch die Anwendung generierte Daten (Caches etc. = temporäre Daten)
*module-Ordner für Applikation-Files!, Controller, Views und tests
*unter public.index.php Initialisierungsdatei, die man nicht ändern muss / sollte

Erklärung des Workflows:
module.config.php (Routen etc.) 
-> lädt Controller 
-> lädt ModelView 
-> lädt layout.phtml - einen Wrapper für css etc., also Default-Layout (phtml enthält wenig Logik im Vergleich zu einer php-Datei)
-> wird gerendert in view

z.B. exisitiert eine Route in der config, bei der ein Controller mit der action index definiert wird. 
Der IndexController hat eine indexAction, die ein ViewModel zurückliefert und wofür es zum einen eine layout.phtml gibt 
und im ordner view->index eine index.phtml

Ausführung mit "php -S localhost:8080 -t public index.php" aus dem Ordner skeleton-applikation oder mit "composer run --timeout 0 serve"


# Run CS checks:
$ composer cs-check
# Fix CS errors:
$ composer cs-fix
# Run PHPUnit tests:
$ composer test --führt die phpunit-Tests aus, alternativ "vendor/bin/phpunit"

Das hier verwendete Projekt hält sich an das Tutorial: https://docs.zendframework.com/tutorials/getting-started/overview/ 

Quellen:
Lynda: https://www.lynda.com/PHP-tutorials/Intro-Zend-3/540346/579823-4.html
https://docs.zendframework.com/tutorials/getting-started/overview/

