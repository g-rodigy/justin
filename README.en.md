![header](https://github.com/martinjack/justin/blob/master/doc/header.png?raw=true)
# Description

[![Latest Stable Version](https://poser.pugx.org/jackmartin/justin/v/stable)](https://packagist.org/packages/jackmartin/justin) [![Total Downloads](https://poser.pugx.org/jackmartin/justin/downloads)](https://packagist.org/packages/jackmartin/justin) [![License](https://poser.pugx.org/jackmartin/justin/license)](https://packagist.org/packages/jackmartin/justin)

PHP class to work with Justin API

> Read this in other language: [English](README.en.md), [Русский](README.md), [Український](README.ua.md)

> [Wiki - Description library](https://github.com/martinjack/justin/wiki)

> [Testing](https://github.com/martinjack/justin/wiki/Tests)

# Documentation

[API documentation](https://justin.ua/api/api_justin_documentation.pdf "PDF")

[Openapi](http://openapi.justin.EN/ "OPENAPI")

# Requirements

* PHP 5.6 or above
* Composer

# Composer
```bash
composer require jackmartin/justin
```

# Libraries

[Guzzle](https://github.com/guzzle/guzzle)

# Basic methods API

1. Setup connection 
    * [__construct](https://github.com/martinjack/justin/blob/master/README.en.md#__construct)
2. Get current status order:
    * [currentStatus](https://github.com/martinjack/justin/blob/master/README.en.md#currentStatus)
3. Get list regions.
    * [listRegions](https://github.com/martinjack/justin/blob/master/README.en.md#listregions)
4. Get list regional areas.
    * [listAreasRegion](https://github.com/martinjack/justin/blob/master/README.en.md#listareasregion)
5. Get list settlements.
    * [listCities](https://github.com/martinjack/justin/blob/master/README.en.md#listcities)
6. Get list areas of settlements
    * [listCityRegion](https://github.com/martinjack/justin/blob/master/README.en.md#listcityregion)
7. Get list streets city.
    * [listStreetsCity](https://github.com/martinjack/justin/blob/master/README.en.md#liststreetscity)
8. Get list types branches
    * [branchTypes](https://github.com/martinjack/justin/blob/master/README.en.md#branchTypes)
9. Get information about department
    * [getBranch](https://github.com/martinjack/justin/blob/master/README.en.md#getBranch)
10. Get list departments. Old method
    * [listDepartments](https://github.com/martinjack/justin/blob/master/README.en.md#listdepartments)
11. Get list departments.
    * [listDepartmentsLang](https://github.com/martinjack/justin/blob/master/README.en.md#listdepartmentslang)
12. Get schedule work branch
    * [branchSchedule](https://github.com/martinjack/justin/blob/master/README.en.md#branchschedule)
13. Get nearest department by address
    * [getNeartDepartment](https://github.com/martinjack/justin/blob/master/README.en.md#getNeartDepartment)
14. Create new order(Departure)
    * [createOrder](https://github.com/martinjack/justi/blob/master/README.en.mdn#createorder)
15. Cancel order
    * [cancelOrder](https://github.com/martinjack/justin#cancelorder)
16. Get list statuses order.
    * [listStatuses](https://github.com/martinjack/justin/blob/master/README.en.md#liststatuses)
17. Get key seller(senderID)
    * [keySeller](https://github.com/martinjack/justin/blob/master/README.en.md#keyseller)
18. Get tracking history
    * [trackingHistory](https://github.com/martinjack/justin/blob/master/README.en.md#trackingHistory)
19. Get localities
    * [localities](https://github.com/martinjack/justin#localities)
20. Get information available services
    * [services](https://github.com/martinjack/justin#services)
21. Get story statuses order. Old method
    * [getStatusHistory](https://github.com/martinjack/justin/blob/master/README.en.md#getstatushistory)
22. Get story statuses order.
    * [getStatusHistoryF](https://github.com/martinjack/justin/blob/master/README.en.md#getstatushistoryf)
23. Get list orders for specified period
    * [listOrders](https://github.com/martinjack/justi/blob/master/README.en.mdn#listorders)
24. Get information about order
    * [orderInfo](https://github.com/martinjack/justin/blob/master/README.en.md#orderinfo)
25. Create sticker order
    * [createSticker](https://github.com/martinjack/justin/blob/master/README.en.md#createsticker)

# Examples

### __construct()

```php
use Justin\Justin;

include_once 'vendor/autoload.php';

$justin = new Justin('EN', true, 'v2', 30, 30, 'UTC');
```

### currentStatus()

```php
include_once 'vendor/autoload.php';

use Justin\Justin;

$justin = new Justin('EN', true);

$justin->setLogin('Your login')->setPassword('Your password');

print_r(

    $justin->currentStatus('201971185')->getData()

);
```

### listRegions()

```php
use Justin\Justin;

include_once 'vendor/autoload.php';

$justin = new Justin('EN', true);

$justin->setLogin('Your login')->setPassword('Your password');

print_r(

    $justin->listRegions()->getData()

);
```

### listAreasRegion()

```php
use Justin\Justin;

include_once 'vendor/autoload.php';

$justin = new Justin('EN', true);

$justin->setLogin('Your login')->setPassword('Your password');

print_r(

    $justin->listAreasRegion()

);
```

### listCities()

```php
use Justin\Justin;

include_once 'vendor/autoload.php';

$justin = new Justin('EN', true);

$justin->setLogin('Your login')->setPassword('Your password');

print_r(

    $justin->listCities()

);
```

### listCityRegion()

```php
use Justin\Justin;

include_once 'vendor/autoload.php';

$justin = new Justin('EN', true);

$justin->setLogin('Your login')->setPassword('Your password');

print_r(

    $justin->listCityRegion()

);
```

### listStreetsCity()

```php
use Justin\Justin;

include_once 'vendor/autoload.php';

$justin = new Justin('EN', true);

$justin->setLogin('Your login')->setPassword('Your password');

print_r(

    $justin->listStreetsCity(

        [

            [

                'name'       => 'objectOwner',

                'comparison' => 'equal',

                'leftValue'  => '32b69b95-9018-11e8-80c1-525400fb7782',

            ]

        ]

    )

    // $justin->name('objectOwner')->leftValue('32b69b95-9018-11e8-80c1-525400fb7782')->equal()->listStreetsCity()
    // $justin->name('objectOwner')->equal('32b69b95-9018-11e8-80c1-525400fb7782')->listStreetsCity()

);
```

### branchTypes()

```php
use Justin\Justin;

include_once 'vendor/autoload.php';

$justin = new Justin('RU', true);

$justin->setLogin('Your login')->setPassword('Your password');

print_r(

    $justin->branchTypes()->getData()

);
```

### getBranch()

```php
use Justin\Justin;

include_once 'vendor/autoload.php';

$justin = new Justin('EN', true);

print_r(

    $justin->getBranch('220')->getData()
    // $justin->getBranch('220')->fields()->number()
    // $justin->getBranch('220')->fields()->getType()
    // $justin->getBranch('220')->fields()->address()
    // $justin->getBranch('220')->fields()->getPosition()
    // $justin->getBranch('220')->fields()->getDescr()
    // $justin->getBranch('220')->fields()->scheduDescr()

);
```

### listDepartments()

```php
use Justin\Justin;

include_once 'vendor/autoload.php';

$justin = new Justin('EN', true);

$justin->setLogin('Your login')->setPassword('Your password');

print_r(

    $justin->listDepartments()

);
```

### listDepartmentsLang()

```php
use Justin\Justin;

include_once 'vendor/autoload.php';

$justin = new Justin('EN', true);

$justin->setLogin('Your login')->setPassword('Your password');

print_r(

    $justin->listDepartmentsLang()

);
```

### branchSchedule()

```php
use Justin\Justin;

include_once 'vendor/autoload.php';

$justin = new Justin('RU', true);

$justin->setLogin('Ваш логин')->setPassword('Ваш пароль');

print_r(

    $justin
    ->name('Depart')
    ->equal('1a4df005-5d8d-11e8-80be-525400fb7782')
    ->branchSchedule()
    ->getData()

);
```

### getNeartDepartment()

```php

use Justin\Justin;

include_once 'vendor/autoload.php';

$justin = new Justin('EN', true);

print_r(

    $justin->getNeartDepartment('Київ,Шевченка,30')->getData()
    // $justin->getNeartDepartment('Київ,Шевченка,30')->fields()->getPosition()
    // $justin->getNeartDepartment('Київ,Шевченка,30')->fields()->distance()
    // $justin->getNeartDepartment('Київ,Шевченка,30')->fields()->format()
    // $justin->getNeartDepartment('Київ,Шевченка,30')->fields()->number()
    // $justin->getNeartDepartment('Київ,Шевченка,30')->fields()->address()
);
```

### cancelOrder()

```php
include_once 'vendor/autoload.php';

use Justin\Justin;

$justin = new Justin('EN', false);


$justin->setKey('Your key API');

print_r(

    $justin->cancelOrder('Code order')->getData()

);

```

### listStatuses()

```php
use Justin\Justin;

include_once 'vendor/autoload.php';

$justin = new Justin('EN', true);

$justin->setLogin('Your login')->setPassword('Your password');

print_r(

    $justin->listStatuses()

);
```

### keySeller()

```php
use Justin\Justin;

include_once 'vendor/autoload.php';

$justin = new Justin('EN', true);

$justin->setLogin('Your login')->setPassword('Your password');

print_r(

    $justin->keySeller(

        [

            [

                'name'       => 'login',

                'comparison' => 'equal',

                'leftValue'  => 'test',

            ],

        ]

    )
    
    // $justin->name('login')->leftValue('test')->equal()->keySeller()
    // $justin->name('login')->equal('test')->keySeller()

);
```

### trackingHistory()

```php
include_once 'vendor/autoload.php';

use Justin\Justin;

$justin = new Justin('EN', true);

print_r(

    $justin->trackingHistory('201810165')->getData()
    // $justin->trackingHistory('201810165')->fields()->orderNumber()
    // $justin->trackingHistory('201810165')->fields()->orderDescr()
    // $justin->trackingHistory('201810165')->fields()->status()
    // $justin->trackingHistory('201810165')->fields()->date()
    // $justin->trackingHistory('201810165')->fields()->time()
    // $justin->trackingHistory('201810165')->fields()->dateAdded()
    // $justin->trackingHistory('201810165')->fields()->deparNumber()
    // $justin->trackingHistory('201810165')->fields()->deparAddress()

);
```

### localities()

```php

include_once 'vendor/autoload.php';

use Justin\Justin;

$justin = new Justin('RU', true);

print_r(

    $justin->localities()
    // $justin->localities('all')
    // $justin->localities('activity')

);
```

### services()

```php

include_once 'vendor/autoload.php';

use Justin\Justin;

$justin = new Justin('RU', true);

print_r(

    $justin->services()

);
```

### getStatusHistory()

```php
use Justin\Justin;

include_once 'vendor/autoload.php';

$justin = new Justin('EN', true);

$justin->setLogin('Your login')->setPassword('Your password');

print_r(

    $justin->getStatusHistory(

        [

            [

                'name'       => 'orderNumber',

                'comparison' => 'equal',

                'leftValue'  => '000000004',

            ],

        ]

    )

    // $justin->name('orderNumber')->leftValue('000000004')->equal()->getStatusHistory()
    // $justin->name('orderNumber')->equal('000000004')->getStatusHistory()

);
```

### getStatusHistoryF()

```php
use Justin\Justin;

include_once 'vendor/autoload.php';

$justin = new Justin('EN', true);

$justin->setLogin('Your login')->setPassword('Your password');

$justin->setKey('Ваш ключ API');

print_r(

    $justin->getStatusHistoryF(

        [

            'name'       => 'orderNumber',

            'comparison' => 'equal',

            'leftValue'  => '000000004',

        ]

    )

    // $justin->name('orderNumber')->leftValue('000000004')->equal()->getStatusHistory()
    // $justin->name('orderNumber')->equal('000000004')->getStatusHistory()

);
```
### createOrder()

#### Пример 1

```php
include_once 'vendor/autoload.php';

use Justin\Order;

$order = new Order('EN', true);

$order->setKey('Your key');

$newOrder = $order
    ->setNumber('52525')
    ->setDate()
    ->senderCityID(

        '32b69b95-9018-11e8-80c1-525400fb7782'

    )
    ->sender('ТОП ПРОДАЦЕЦ')
    ->senderContact('Иванов Иван')
    ->senderPhone('380524152299')
    ->addressPickup('ул. Груша. 7')
    ->requirePickup(true)
    ->senderBranchID(

        '2100102032'

    )
    ->receiver('ТОВ Укрпочта')
    ->receiverContact('Петр 1')
    ->receiverPhone('380425831259')
    ->countPlace(1)
    ->receiverBranchID(

        '2100108028'

    )
    ->volume('0.02')
    ->weight('100')
    ->costDeclared(1500)
    ->deliveryAmount(0)
    ->redeliveryAmount(1500)
    ->orderAmount(1500)
    ->redeliveryPay(true)
    ->redeliveryPayer(1)
    ->deliveryPay(true)
    ->deliveryPayer(1)
    ->requireDelivery(false)
    ->orderPay(true)
    ->comment('Тест заказ')
    ->createOrder();

print_r(

    $newOrder->fields()->number()
    // $newOrder->fields()->ttn()
    // $newOrder->getData()
    // $newOrder->getResult()
    // $newOrder->getRaw()

);

```

#### Пример 2

```php
include_once 'vendor/autoload.php';

use Justin\Order;

$order = new Order('EN', true);

$order->setKey('Your key');

$newOrder = $order->createOrder(

    [
        'number'                         => '123456',

        'date'                           => '20171221',

        'sender_city_id'                 => '32b69b95-9018-11e8-80c1-525400fb7782',

        'sender_company'                 => 'УА ТОВ',

        'sender_contact'                 => 'Петрова Ирина',

        'sender_phone'                   => '+380991112233',

        'sender_pick_up_address'         => 'Степана Бандери, No 6',

        'pick_up_is_required'            => true,

        'sender_branch'                  => '2100102032',

        'receiver'                       => 'Петров Сергей',

        'receiver_contact'               => '',

        'receiver_phone'                 => 'Петров Сергей',

        'count_cargo_places'             => 2,

        'branch'                         => '2100108028',

        'weight'                         => 0.1,

        'volume'                         => 0.02,

        'declared_cost'                  => 1500,

        'delivery_amount'                => 0,

        'redelivery_amount'              => 1500,

        'order_amount'                   => 1500,

        'redelivery_payment_is_required' => true,

        'redelivery_payment_payer'       => 1,

        'delivery_payment_is_required'   => true,

        'delivery_payment_payer'         => 1,

        'delivery_is_required'           => false,

        'order_payment_is_required'      => true,

        'add_description'                => 'Тест API'
    ]

);

print_r(

    $newOrder->fields()->number()
    // $newOrder->fields()->ttn()
    // $newOrder->getData()
    // $newOrder->getResult()
    // $newOrder->getRaw()

);
```

### listOrders()

```php
use Justin\Justin;

include_once 'vendor/autoload.php';

$justin = new Justin('RU', true);

$justin->setKey('Ваш ключ');

print_r(

    $justin->listOrders('20190505')->getData()

);
```

### orderInfo()

```php
use Justin\Justin;

include_once 'vendor/autoload.php';

$justin = new Justin('RU', true);

$justin->setKey('Ваш ключ');

print_r(

    $justin->orderInfo('Your order number')->getData()

);
```

### createSticker()

```php
use Justin\Justin;

include_once 'vendor/autoload.php';

$justin = new Justin('EN', true);

$justin->setKey('Your key');

print_r(

    $justin->createSticker(

        '877893', __DIR__ . '/' . time() . '.pdf'

    )

);

print_r(

    $justin->createSticker(

        '877893', __DIR__ . '/' . time() . '.pdf', false, 1

    )

);

print_r(

    $justin->createSticker(

        '877893', __DIR__ . '/' . time() . '.pdf', false, 2

    )

);

print_r(

    $justin->createSticker(

        '877893', true

    )

);

print_r(

    $justin->createSticker(

        '877893', true, 'url'

    )

);
```
### Sticker has name or FIO sender and receiver
![Sticker1](https://github.com/martinjack/justin/blob/master/doc/sticker1.png?raw=true "Example sticker order. Sticker has name or FIO sender and receiver")
### Sticker has names sender and receiver
![Sticker2](https://github.com/martinjack/justin/blob/master/doc/sticker2.png?raw=true "Example sticker order. Sticker has names sender and receiver")
### Sticker has address receiver, if delivery was made at the address
![Sticker2](https://github.com/martinjack/justin/blob/master/doc/sticker3.png?raw=true "Example sticker order. Sticker has address receiver, if delivery was made at the address")