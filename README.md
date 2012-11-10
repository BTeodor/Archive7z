# ������ � 7z �������� � ������� ��������� ������.

�� ������ ������, �������������� ���������� ����� ������,
���������� ����� ���������� ��� ����� � ������,
�������� ���� ������ � ���������� ����������� � ������,
��������� ����������� ����� � ������.

������:
```php
<?php
set_include_path(__DIR__);
require 'Archive/7z.php';

$obj = new Archive_7z('./test.7z');
$obj->setOutputDirectory('./test');

foreach ($obj->getEntries() as $v) {
    if ($v->getName() === 'test.txt') {
        print_r($v);
        $v->extractTo('./test2');
    }
}

echo $obj->getContent('test.txt');

$obj->extract();
```