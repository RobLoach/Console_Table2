This package is http://pear.php.net/package/Console_Table2

== Migrating from Console_Table ==
 * Swap all CONSOLE_TABLE_* constants to Console_Table2::*
 * Swap Console_Table to Console_Table2, require_once 'Console/Table.php' =>  require_once 'Console/Table2.php'
 * Instead of being a boolean for $color, simply instantiate a new Console_Color2 or use the appropriate setter

	require_once 'Console/Table2.php';
	require_once 'Console/Color2.php';

	$color = new Console_Color2();

	$table = new Console_Table2(Console_Table2::ALIGN_LEFT, Console_Table2::BORDER_ASCII, 1);
	$table->setColor($color);
	$table->setHeaders(array('foo', 'bar'));
	$table->addRow(array('baz', $color->convert("%bblue%n")));

	echo $table->getTable();

== Building ==


Please report all new issues via the PEAR bug tracker.

If this package is marked as unmaintained and you have fixes, please submit your pull requests and start discussion on the pear-qa mailing list.

To test, run either
$ phpunit tests/
  or
$ pear run-tests -r

To build, simply
$ pear package

To install from scratch
$ pear install package.xml

To upgrade
$ pear upgrade -f package.xml
