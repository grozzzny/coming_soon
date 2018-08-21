Coming Soon for yii2 - страница заглушка
==============================

## Installation guide
```bash
$ php composer.phar require grozzzny/coming_soon "dev-master"
```

\config\web.php

```php

$config = [
    ...
    'components' => [
        ...
    ],
    ...
    //coming_soon
    'on beforeAction' => function() {
        if(isset($_GET['open'])){
            setcookie("dev","true",time() + 30*24*60*60);
            exit('<html><head><meta http-equiv="refresh" content="0;/"></head><body></body></html>');
        }
    },
    'params' => $params,
];

if (empty($_COOKIE['dev'])) {
    $config['modules']['coming_soon'] = [
        'class' => 'grozzzny\coming_soon\ComingSoonModule',
        'settings' => [
            'title' => 'АМБАР - купить продукты по низким ценам',
            'heading' => 'Сайт в разработке',
            'descriptions' => 'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Iure perspiciatis quod, voluptatum, porro pariatur facere id in unde obcaecati nobis sapiente cupiditate ipsa veniam quam natus voluptate ipsum minima soluta!',
            'address' => 'One infinity loop, 54100',
            'phone' => '+00 1234567890',
            'email' => 'youremail@domain.com',
            'expiryDate' => '2018/08/31',
            'copyright' => 'www.ambar39.ru. All rights reserved.',
        ]
    ];
    $config['catchAll'] = ['coming_soon'];
}

return $config;

```
