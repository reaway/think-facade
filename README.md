# think-facade

## 安装
```bash
composer require reaway/think-facade
```

## 用法
定义一个`app\facade\App`类之后，即可以静态方式调用`\think\App`类的动态方法
```php
<?php

namespace think;

class App
{
    public function name()
    {
        return 'app';
    }
}
```

```php
<?php

namespace app\facade;

use think\Facade;

class App extends Facade
{
    /**
     * 获取当前Facade对应类名
     * @access protected
     * @return string
     */
    protected static function getFacadeClass()
    {
        return '\think\App';
    }
}
```

然后就可以静态方式调用动态方法了
```php
use app\facade\App;

echo App::name(); // app
```