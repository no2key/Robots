# Robots.txt

## Test with [Atoum](https://github.com/mageekguy/atoum)

	cd Robots/
	php src/mageekguy.atoum.phar -d Tests/Units/
	
## Reader

``` php
<?php
namespace Application;

require_once __DIR__ . '/../src/Robots/Reader.php';

use Robots;

$r = new Robots\Reader();
print_r($r->parse(
	file_get_contents(Robots\Reader::url('http://www.robotstxt.org'))
));

?>
```

Output

	Array(
		[User-agent] => Array(
			[0] => Array(
				[Name] => *
			)
			[1] => Array(
				[Name] => litefinder
				[Disallow] => Array(
					[0] => /
				)
			)
			[2] => Array(
				[Name] => Slurp
				[Disallow] => Array(
					[0] => /
				)
			)
			[3] => Array(
				[Name] => Baidu
				[Disallow] => Array(
					[0] => /
				)
			)
		)
	)
