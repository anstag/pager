# Pager
Pager library to split results into multiple pages
  
## Install
Via Composer
  
``` bash
$ composer require anstag/pager
```
  
## Usage
``` php
$obj = new Anstag\Pager\DirPager(
    new Anstag\Pager\PagesList(),
    'photos',
    3,
    2
);

echo "<pre>";
print_r($obj->getItems());
echo "</pre>";

echo "<p>$obj</p>";
```
  
``` php
$obj = new Anstag\Pager\FilePager(
    new Anstag\Pager\ItemsRange(),
    'largetextfile.txt'
);
    
echo "<pre>";
print_r($obj->getItems());
echo "</pre>";

echo "<p>$obj</p>";
```
  
``` php
try {
    $pdo = new PDO(
        'mysql:host=localhost;dbname=test',
        'root',
        '',
        [PDO::ATTR_ERRMODE => PDO::ERRMODE_EXCEPTION]
    );
    
    $obj = new Anstag\Pager\PdoPager(
        new Anstag\Pager\ItemsRange(),
        $pdo,
        'table_name'
    );
    
    echo "<pre>";
    print_r($obj->getItems());
    echo "</pre>";
    
    echo "<p>$obj</p>";
} catch (PDOException $e) {
    echo "Can't connect to database";
}
```
  
## License
The MIT License (MIT).