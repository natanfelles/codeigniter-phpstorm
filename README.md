# PhpStorm Code Completion to CodeIgniter + HMVC

Working perfectly with CodeIgniter 3.1.0

### How to use it:

1. Drop the **phpstorm.php** file into your CI project root then PhpStorm will index it.
2. Go to *system/core/* folder.
3. Select *Controller.php* and *Model.php* files, right click and set *Mark as Plain Text*.

### HMVC Support

If you are using the Modular HMVC, mark as Plain Text the Controller.php file in the MX folder.

You need to add the `@property` tag in the class doc block:

```php
/**
 * Class Cart
 * @property Cart $cart Cart module
 */
class Cart extends MX_Controller {

	/**
	 * Add product to cart
	 * @param int $id Product id
	 */
	public function add($id = 0)
	{
		// Do it...
	}
}
```

To load modules in other places do like it:

```php
/**
 * @var Cart $cart This will provide Code Completion in the $cart variable
 */
$cart = Modules::load('cart');
```

Use *Ctrl + Q* in `$cart` to load documentation or help with available functions:

```php
$cart->add(5);
```

### Usage in Views

If you want load CI_Controller or MX_Controller in a view, add a doc block as follow:

```php
/**
 * @var CI_Controller $this
 */
echo $this->uri->segment(1);
````

### Preview:
![Image of Code Completion](https://raw.githubusercontent.com/natanfelles/codeigniter-phpstorm/master/codeigniter-phpstorm.png)

