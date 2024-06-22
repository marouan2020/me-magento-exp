# Magento 2 Troubleshooting

Table of Contents
=================

* [Magento 2 Troubleshooting]()
* [Table of Contents]()
    * [Debugging]()
        * [Debugging procedure using the DevBox and XDebug]()
            * [Browser debugging]()
            * [Command line debugging]()
        * [Profiling]()
            * [Profiling API requests]()
        * [Creating a basic test rig bootstrapping script]()
            * [One-file Magento bootstrapper]()
            * [Two-file Magento bootstrapper]()
    * [Installation/upgrade]()
        * ["Magento\InventoryApi\Model\SourceValidatorInterface" not found in vendor/magento/module-inventory-in-store-pickup/Model/Source/Validator/StreetValidator.php:19]()
        * [Uncaught Error: Interface "Magento\InventorySourceSelectionApi\Model\GetSourceItemQtyAvailableInterface" not found in vendor/magento/module-inventory-in-store-pickup-sales/Model/SourceSelection/GetSourceItemQtyAvailableService.php:24]()
        * [Uncaught Error: Interface "Magento\InventoryCatalogSearch\Model\Indexer\SelectModifierInterface" not found in vendor/magento/module-inventory-catalog-search-bundle-product/Model/CatalogSearch/Indexer/BundleChildStockStatusModifier.php:22]()
        * [Uncaught Error: Interface "Magento\InventoryCatalogSearch\Model\Indexer\SelectModifierInterface" not found in vendor/magento/module-inventory-catalog-search-configurable-product/Model/CatalogSearch/Indexer/ConfigurableChildStockStatusModifier.php:22]()
        * [Uncaught Error: Interface "Magento\QuoteGraphQl\Model\Cart\MergeCarts\CartQuantityValidatorInterface" not found in vendor/magento/module-inventory-quote-graph-ql/Model/Cart/MergeCarts/CartQuantityValidator.php:19]()
        * [ Uncaught Error: Interface "Magento\QuoteGraphQl\Model\Cart\Payment\AdditionalDataProviderInterface" not found in vendor/paypal/module-braintree-graph-ql/Model/BraintreeDataProvider.php:16]()
        * [Uncaught Error: Interface "Magento\GraphQl\HelperrrorxceptionMessageFormatterInterface" not found in vendor/magento/module-payment-graph-ql/Helper/Error/MessageFormatters/GatewayCommandExceptionMessageFormatter.php:21]()
        * [Uncaught Error: Class "Staempfli\ImageResizer\Model\Resizer" not found in app/code/VendorName/Downloads/Model/Resizer.php:17]()
        * [Unable to apply data patch Magento\CatalogRuleSampleData\Setup\Patch\Data\InstallCatalogRuleSampleData for module Magento_CatalogRuleSampleData. Original exception message: Rolled back transaction has not been completed correctly. or Unable to apply data patch Magento\SalesRuleSampleData\Setup\Patch\Data\InstallSalesRuleSampleData for module Magento_SalesRuleSampleData. Original exception message: Rolled back transaction has not been completed correctly.]()
        * [amasty_label view does not exist.]()
        * [class_alias(): Argument #1 ($class) must be a user-defined class name, internal class name given]()
        * [Magento/PHP reports missing extensions, even though they are present in phpinfo]()
        * [Feb 22 14:58:08 zone8-aurora-r5 nginx[28734]: nginx: [emerg] "fastcgi_busy_buffers_size" must be less than the size of all "fastcgi_buffers" minus one buffer in /etc/nginx/nginx.conf:58]()
        * [Notice: Undefined index: sections]()
        * [After 2.3.0 upgrade 'Zend\Mvc\Controller\LazyControllerAbstractFactory' not found]()
        * [Undefined offset: 2 in vendor/magento/framework/Encryption/Encryptor.php on line 588]()
        * [Error during Magento 2 upgrade: “File doesn’t exist: bin/magento”]()
        * [Warning: call_user_func() expects parameter 1 to be a valid callback, class 'Vendor\Module\Setup\Patch\Data\DeleteInvalidCompanyAdvancedCustomerEntityRows' not found in /var/www/html/example-project/html/vendor/magento/framework/Setup/Patch/PatchRegistry.php on line 141]()
        * [[Magento\Framework\SetupException] Unable to apply patch Vendor\ModuleName\Setup\Patch\Schema\MageplazaAttributesCleanup for module Vendor_ModuleName. Original exception message: Invalid entity_type specified: catalog_product]()
        * [SQLSTATE[42S22]: Column not found: 1054 Unknown column 'e.customer_type' in 'field list']()
    * [Upgrading]()
        * [magento/magento2-functional-testing-framework[3.7.0, ..., 3.11.1] require guzzlehttp/guzzle ^7.3.0 -&gt; found guzzlehttp/guzzle[7.3.0, ..., 7.5.0] but it conflicts with your root composer.json require (6.3.3).]()
    * [Admin]()
        * [Class Magento\Logging\Model\Source\Frequency does not exist]()
        * [MySQL adapter: Missing required configuration option 'host']()
        * [Notice: SessionHandler::gc(): ps_files_cleanup_dir: opendir(/var/lib/php/sessions) failed: Permission denied]()
        * [Class argument is invalid: Magento\Framework\Viewement\UiComponent\Context]()
        * [Something went wrong with reCAPTCHA. Please contact the store owner.]()
        * [Default Product Listing Sort by does not exist in Available Product Listing Sort By.]()
        * [Fatal error: Cannot declare class Zend_Http_Client, because the name is already in use in .../vendor/magento/zendframework1/library/Zend/Http/Client.php on line 72]()
        * [Uncaught ReflectionException: Class Magento\Framework\App\ResourceConnection\Proxy does not exist in /var/www/html/m2/research/m24-example-modules/html/vendor/magento/framework/Code/Reader/ClassReader.php:34]()
        * [Fatal error: Uncaught TypeError: Argument 2 passed to Magento\Framework\Viewement\UiComponentFactory::argumentsResolver() must be of the type array, null given, called in ../vendor/magento/framework/View/Element/UiComponentFactory.php on line 208 and defined in ../vendor/magento/framework/View/Element/UiComponentFactory.php:174]()
        * [Trying to load example.com/admin produces 404]()
        * [Call to undefined method ProcessEight\LayeredNavCustomSeo\Model\CrawlableRepository::create() in /var/www/html/m2/research/m23-example-modules/html/app/code/ProcessEight/LayeredNavCustomSeo/Plugin/Eav/Block/Adminhtml/Attribute/Edit/Options/OptionsPlugin.php]()
        * [Could not create an acl object: Invalid Document]()
        * [Cannot login to admin: 'Too many redirects']()
        * [Exception #0 (Magento\Frameworkxception\RuntimeException): Type Error occurred when creating object: Trespass\ApproveSuspectedFraudOrders\Controller\Adminhtml\Payment\Approve\Interceptor]()
        * [DateTime::__construct(): Failed to parse time string (19/10/2018 00:00) at position 0 (1): Unexpected character]()
        * ['PHP Notice in magento 2.2: Notice: Undefined index: id in vendor/magento/module-config/Model/Config/Structure/Element/Iterator.php on line 63' when trying to access Stores &gt; Configuration in M2.2]()
        * ['The value of attribute "..." must be set' when adding a new customer attribute]()
        * [Styles appear in frontend and on admin login page, but not in admin panel after logging in]()
        * [PHP Fatal error: 'Cannot declare class because the name is already in use']()
        * [Exception #0 (ReflectionException): Class Magento\Framework\Viewement\UiComponent\DataProvider\DataProvider does not exist]()
        * [Call to undefined method Magento\Framework\Controller\Result\Forward\Interceptor::create() in /var/www/vhosts/m2-example-modules.localhost.com/app/code/ProjectEight/PersistenceLayerExample/Controller/Adminhtml/WhatsIt/NewAction.php:49]()
        * [Uncaught TypeError: Argument 5 passed to ProjectEight\PersistenceLayerExample\Controller\Adminhtml\WhatsIt::__construct() must be an instance of Magento\Backend\Model\View\Result\ForwardFactory, none given, called in /var/www/vhosts/m2-example-modules.localhost.com/var/generation/ProjectEight/PersistenceLayerExample/Controller/Adminhtml/WhatsIt/Edit/Interceptor.php on line 14 and defined in /var/www/vhosts/m2-example-modules.localhost.com/app/code/ProjectEight/PersistenceLayerExample/Controller/Adminhtml/WhatsIt.php:54]()
        * [Not registered handle]()
        * [Magento can generate files when invoked using bin/magento setup:di:compile, but not when invoked during code execution (i.e. Loading a page, running a (different) bin/magento command)]()
        * [Notice: Undefined offset: 2 in /www/web/demo/vendor/magento/framework/Encryption/Encryptor.php]()
        * [Area code is not set]()
        * [Logged out when browsing the 'Edit Product' page]()
        * [Exception #0 (Zend_Db_Statement_Exception): SQLSTATE[42S22]: Column not found: 1054 Unknown column '' in 'where clause', query was: SELECT COUNT(*) FROM moorelarge_feedprocessorbase_message AS main_table WHERE ('' IN('3', '4'))]()
    * [Elasticsearch]()
        * [{"error":{"root_cause":[{"type":"cluster_block_exception","reason":"blocked by: [FORBIDDEN/12/index read-only / allow delete (api)];"}],"type":"cluster_block_exception","reason":"blocked by: [FORBIDDEN/12/index read-only / allow delete (api)];"},"status":403}]()
        * [Elasticsearch totally fails to start]()
        * [Cannot start Elasticsearch; Elasticsearch starts but fails almost immediately]()
        * [Cannot save stock items or products, e.g. The stock item was unable to be saved]()
        * [Exception #0 (Elasticsearch\Commonxceptions\NoNodesAvailableException): No alive nodes found in your cluster]()
        * [Elasticsearch is running, but cannot connect to <a href="http://localhost:9200/" rel="nofollow">http://localhost:9200/</a>](http://localhost:9200/)
        * [Elasticsearch is running, but cannot create catalog_product index]()
        * [Catalog Search indexer process unknown error: Indexer handler is not available: elasticsuite]()
        * [General debugging tips for Elasticsearch]()
    * [CLI]()
        * [Incompatible argument type: Required type: \Amasty\ShopbyBase\Model\FilterSettingFactory. Actual type: \Magento\Framework\App\Helper\Context; File:]()
        * ['Interface 'Vertex\Tax\Model\Flexfield\Processor\InvoiceFlexFieldProcessorInterface' not found' when running setup:di:compile' command]()
        * ['There are no commands defined in the ... namespace']()
        * ['Class ProcessEight\ModuleManager\Command\Module\Add\BinMagentoCommandCommand\Interceptor does not exist']()
    * [Frontend]()
        * [No styles on frontend]()
        * [Exception #0 (Magento\Frameworkxception\FileSystemException): The path "/var/www/html/m2/research/m24-example-modules/html/pub/static/." is not writable.]()
        * [The files in my custom adminhtml theme are being ignored by Magento]()
        * [Cannot load fonts or XMLHttpRequest]()
        * [Debugging frontend assets]()
        * [Random 404 errors]()
        * [Seeing the server 404 page rather than the Magento one]()
        * [Unable to retrieve deployment version of static files from the file system.]()
        * [[Exception] Warning: Invalid argument supplied for foreach() in /vendor/magento/module-store/Model/Config/Processor/Fallback.php on line 125]()
        * [Frontend asset URLs of the kind http://www.example.co.uk/pub/static/version1510670604/frontend/Magento/luma/en_GB/mage/calendar.css return a 404, even if <code>frontend/Magento/luma/en_GB/mage/calendar.css</code> does actually exist.]()
        * [Failed to load the "ProcessEight_CheckoutAddComponentToSidebarExample/js/view/FoolSample" component]()
        * [Unable to resolve the source file for 'frontend/Magento/luma/en_GB/ProcessEight_CheckoutAddComponentToSidebarExample/template/checkout/foolsample.html']()
        * [My controller is not loading my layout updates]()
        * [My template is not rendered at all]()
        * [Exception #0 (Magento\Frameworkxception\LocalizedException): Object DOMDocument should be created.]()
        * [Path "/var/www/html/m23-example-modules/htdocs/pub/static/" cannot be used with directory "/var/www/html/m23-example-modules/htdocs/pub/static/]()
        * [Required parameter 'theme_dir' was not passed]()
        * [Refused to apply style from 'http://m23-example-modules.local/static/version1561564942/frontend/ProcessEight/ExampleTheme/en_GB/css/styles-m.css' because its MIME type ('text/plain') is not a supported stylesheet MIME type, and strict MIME checking is enabled]()
        * [JS objects are not of the expected type (e.g. They are instantiated as instances of jquery-ui)]()
        * [Assets are served over HTTPS, despite  the <code>web/secure/base_url</code> being set to a <code>http://...</code> address]()
        * ['We can't save the address: Email has a wrong format']()
        * [Category titles appear with a different case on the frontend than on the backend]()
    * [Email]()
        * [Ordered products table does not appear in the Order Email Template]()
    * [Hyva]()
        * [[InvalidArgumentException] Could not find a matching version of package hyva-themes/magento2-reset-theme. Check the package spelling, your version constraint and that the package is available in a stability which matches your minimum-stability (stable).]()
    * [MySQL]()
        * [mysqldump: Couldn't execute 'SHOW FUNCTION STATUS WHERE Db = 'magento2'': Column count of mysql.proc is wrong. Expected 21, found 20. Created with MariaDB 50717, now running 100427. Please use mysql_upgrade to fix this error (1558)]()
        * [Types char is not declared]()
        * [Delete duplicate rows from a table]()
        * [Output query into TSV file]()
        * [Import CSV file]()
            * [From the CLI]()
            * [From inside mysql]()
            * [Replicating 'upsert' behaviour]()
        * [1148: The used command is not allowed with this MySQL version]()
        * [The LOAD DATA query executes without error, but doesn't import anything - even if I move my file to the secure_file_priv location (usually <code>/var/lib/mysql-files/</code>)]()
        * [Enabling local_infile in Magento 2]()
        * [ERROR 1227 (42000) at line 16149: Access denied; you need (at least one of) the SUPER privilege(s) for this operation]()
        * ['Access denied; you need (at least one of) the PROCESS privilege(s) for this operation' when trying to dump tablespaces]()
    * [Nginx]()
        * [Upstream sent too big header while reading response header from upstream]()
    * [RabbitMQ]()
    * [JavaScript]()
        * [Mixin does not work]()
    * [Resource scripts]()
        * [Setup script never runs]()
    * [Permissions]()
        * [Verify that permissions are setup correctly]()
    * [Performance]()
    * [Deployment]()
        * [Magento Cloud]()
            * [error: pub/front-static.php: No such file or directory]()
    * [Magento Enterprise/Commerce Edition]()
        * [All products disappear from categories on the frontend, but still appear in the admin]()
    * [Extensions]()
        * [Ebizmarts SagePaySuite/Opayo]()
    * [WordPress integrations]()
        * [WordPress API not available. Hello (<a href="http://example.local/wp/index.php?rest_route=/fishpig/v1/hello" rel="nofollow">http://example.local/wp/index.php?rest_route=/fishpig/v1/hello</a>) failed.](http://example.local/wp/index.php?rest_route=/fishpig/v1/hello)
    * [Tools]()
        * [Composer]()
            * [Composer doesn't apply patches]()
        * [PhpStorm]()
            * [PHP CS Fixer: PHP needs to be a minimum version of PHP 5.3.6 and maximum version of PHP 7.3.* (even if configured PHP language level is 7.3 or lower)]()
            * [PhpStorm is stuck on Updating indexes]()
        * [Magicento]()
            * [Magicento 2 plugin for PhpStorm gives an error about the 'PHP response not being correct' or similar]()
                * [Magicento 2 still doesn't work]()
                * [Deprecation messages appearing in the PhpStorm Event Log]()
        * [Xdebug]()
            * [Installing/upgrading]()
            * [Error message: Xdebug requires Zend Engine API version 320190902. The Zend Engine API version 320180731 which is installed, is outdated.]()
            * [Xdebug won't start]()
        * [Configuring Xdebug 3]()

Created by [gh-md-toc](https://magento-tunisia.com/)

## Debugging

### Debugging procedure using the DevBox and XDebug

#### Browser debugging

* Make sure you've setup a server in PhpStorm which has the correct path mappings
* Find out the SSH port of the `web` container:
```bash
$ docker-compose ps
                       Name                                     Command              State                                      Ports                                    
------------------------------------------------------------------------------------------------------------------------------------------------------------------------
magento2devbox_db_2706763fef8613d6b05e75cf8410c36f    docker-entrypoint.sh mysqld    Up      0.0.0.0:32768->3306/tcp                                                     
magento2devbox_web_2706763fef8613d6b05e75cf8410c36f   /usr/local/bin/entrypoint.sh   Up      0.0.0.0:32770->22/tcp, 44100/tcp, 5000/tcp, 0.0.0.0:32769->80/tcp, 9000/tcp
```
In this example the external SSH port 22 is mapped to the internal port 32770 of the web container.
* Add the SSH port to the configured server in PhpStorm
* Enable `Start Listening for debug connections` in PhpStorm.
* Set a breakpoint or enable the `Break on first line in PHP scripts` setting
* Now start an SSH tunnel to the web container, using the `m2devbox-debug.sh` script:
```bash
$ ./m2devbox-debug.sh
```
* Drop the `XDEBUG_SESSION` cookie in the browser. Refresh the page.

#### Command line debugging

* Make sure you've setup a server in PhpStorm which has the correct path mappings
* Login to the `web` Docker container.
* Export the following two variables:
    ```bash
    $ export XDEBUG_CONFIG="idekey=PHPSTORM"
    $ export PHP_IDE_CONFIG="serverName=[Server name from PhpStorm]"
    ```
* Enable `Start listening for debugger connections` in PhpStorm
* Set a breakpoint
* Execute a command line instruction, e.g.
    ```bash
    $ bin/magento indexer:reindex catalog_product_price
    ```
    
_Source: https://confluence.jetbrains.com/display/PhpStorm/Debugging+PHP+CLI+scripts+with+PhpStorm#DebuggingPHPCLIscriptswithPhpStorm-2.StarttheScriptwithDebuggerOptions_

### Profiling

#### Profiling API requests

Unfortunately, it is not possible to profile API requests using the Magento Profiler. This is because the profiler attaches itself to the response to append its' profiling data, which could 'pollute' responses like XML or JSON, which have to be 'clean' (i.e. Contain nothing but XML or JSON). See https://github.com/magento/magento2/blob/2.3-develop/app/bootstrap.php#L53.
_Source: https://pulsestorm.slack.com/archives/C04EYLASQ/p1558121556137200_

### Creating a basic test rig bootstrapping script

#### One-file Magento bootstrapper

```php
<?php
require_once 'app/bootstrap.php';
$bootstrap = \Magento\Framework\App\Bootstrap::create(BP, $_SERVER);
 
// Any code you want here...For example:

$object = $bootstrap->getObjectManager()->create('Namespace\Module\Model\Test');
```

#### Two-file Magento bootstrapper

You need to create two files in order to bootstrap Magento in this test script.
The first is `htdocs/test.php`. It bootstraps the Magento application:
```php
<?php
try {
    require __DIR__ . '/app/bootstrap.php';
} catch (\Exception $e) {
    echo <<<HTML
<div style="font:12px/1.35em arial, helvetica, sans-serif;">
    <div style="margin:0 0 25px 0; border-bottom:1px solid #ccc;">
        <h3 style="margin:0;font-size:1.7em;font-weight:normal;text-transform:none;text-align:left;color:#2f2f2f;">
        Autoload error</h3>
    </div>
    <p>{$e->getMessage()}</p>
</div>
HTML;
    exit(1);
}

$bootstrap = \Magento\Framework\App\Bootstrap::create(BP, $_SERVER);
/** @var \Magento\Framework\App\Http $app */
// Note that the name of the 'app' we are creating is 'TestApp'
$app = $bootstrap->createApplication('TestApp');
$bootstrap->run($app);
```
The second file is `htdocs/TestApp.php`. It contains the actual code we want to test:
```php
<?php

class TestApp extends \Magento\Framework\App\Http implements \Magento\Framework\AppInterface {

    /**
     * @return \Magento\Framework\App\Response\Http
     */
    public function launch()
    {
    	// Add the code you want to test in here.
	// This example shows how to get all the values of a dropdown customer attribute
	
        /** @var \Magento\Framework\App\ObjectManager $objectManager */
        $objectManager = \Magento\Framework\App\ObjectManager::getInstance();

        /** @var \Magento\Eav\Api\AttributeRepositoryInterface $eavAttributeRepository */
        $eavAttributeRepository = $objectManager->create( \Magento\Eav\Api\AttributeRepositoryInterface::class);

        $attribute = $eavAttributeRepository->get(\Magento\Customer\Api\CustomerMetadataInterface::ENTITY_TYPE_CUSTOMER, 'my_dropdown_customer_attribute_code');
        $options = $attribute->getSource()->getAllOptions(false);

        var_export($options);

        // The method must end with this line
        return $this->_response;
    }

    /**
     * @param \Magento\Framework\App\Bootstrap $bootstrap
     * @param Exception                        $exception
     *
     * @return bool
     */
    public function catchException(\Magento\Framework\App\Bootstrap $bootstrap, \Exception $exception)
    {
        return false;
    }
}
```
## Installation/upgrade

### for key 'PRIMARY', query was: ALTER TABLE `catalog_url_rewrite_product_category` ADD CONSTRAINT  PRIMARY KEY (`url_rewrite_id`

Duplicate rows in the `catalog_url_rewrite_produce_category` table prevent a new constraint (e.g. Foreign key) being added. Delete the duplicate rows, or change the conditions of the constraint if possible.

### Undefined array key "inventory_source" in vendor/magento/framework/Setup/Declaration/Schema/Db/SchemaBuilder.php on line 153

Disable MSI and try again.

### Return value of Magento\Framework\Encryption\Adapter\SodiumChachaIetf::decrypt() must be of the type string, boolean returned

If you've imported a db from somewhere else, then use the crypt key from that instances' `app/etc/env.php`.

See https://github.com/magento/magento2/issues/19590#issuecomment-460398632

### Base table or view not found: 1146 Table 'eav_entity_type' doesn't exist

```shell
[Progress: 4 / 1791]
Installing database schema:

In Mysql.php line 603:

  [Magento\Framework\DB\Adapter\TableNotFoundException (1146)]
  SQLSTATE[42S02]: Base table or view not found: 1146 Table 'magento2_integration_tests.eav_entity_type' doesn't exist, query was: SELECT `main_table`.* FROM `eav_entity_type` AS `main_table`
```

A custom module in `app/code` had defined a console command, which injected a catalog class.

Re-defining this dependency as a Proxy class fixed the issue.

### `Fatal error:  During inheritance of JsonSerializable: Uncaught Exception: Deprecated Functionality: Return type of Aheadworks\Layerednav\Ui\Component\MassAction\ChangeStatusInSearchOptions::jsonSerialize() should either be compatible with JsonSerializable::jsonSerialize(): mixed, or the #[\ReturnTypeWillChange] attribute should be used to temporarily suppress the notice in vendor/aheadworks/module-layered-navigation/Ui/Component/MassAction/ChangeStatusInSearchOptions.php on line 84`

This is caused by a PHP-dependency version mismatch. Make sure you're running Composer with the right version of PHP for the project's dependencies.

### `"Magento\InventoryApi\Model\SourceValidatorInterface" not found in vendor/magento/module-inventory-in-store-pickup/Model/Source/Validator/StreetValidator.php:19`

After upgrading to Magento 2.4.5-p1, when running `setup:di:compile`, this error occurs:

```injectablephp
$ php81 n98-magerun2.phar setup:di:compile
PHP 8.1.13 (cli) (built: Nov 26 2022 14:07:18) (NTS)
Copyright (c) The PHP Group
Zend Engine v4.1.13, Copyright (c) Zend Technologies
with Zend OPcache v8.1.13, Copyright (c), by Zend Technologies
Compilation was started.
Repositories code generation... 1/9 [===>------------------------]  11% 1 sec 146.4 MiBPHP Fatal error:  Uncaught Error: Interface "Magento\InventoryApi\Model\SourceValidatorInterface" not found in vendor/magento/module-inventory-in-store-pickup/Model/Source/Validator/StreetValidator.php:19
```

`magento/module-inventory-in-store-pickup` is a new module added to MSI. If the project is not using MSI and has removed them by adding them to the `replace` section of `composer.json`. then `magento/module-inventory-in-store-pickup` will need to be `replace`d in the same way. Run `composer update` afterwards.

### `Uncaught Error: Interface "Magento\InventorySourceSelectionApi\Model\GetSourceItemQtyAvailableInterface" not found in vendor/magento/module-inventory-in-store-pickup-sales/Model/SourceSelection/GetSourceItemQtyAvailableService.php:24`

Same as above, but replace `magento/module-inventory-in-store-pickup-sales` instead

### `Uncaught Error: Interface "Magento\InventoryCatalogSearch\Model\Indexer\SelectModifierInterface" not found in vendor/magento/module-inventory-catalog-search-bundle-product/Model/CatalogSearch/Indexer/BundleChildStockStatusModifier.php:22`

Same as above, but replace `magento/module-inventory-catalog-search-bundle-product` instead

### `Uncaught Error: Interface "Magento\InventoryCatalogSearch\Model\Indexer\SelectModifierInterface" not found in vendor/magento/module-inventory-catalog-search-configurable-product/Model/CatalogSearch/Indexer/ConfigurableChildStockStatusModifier.php:22`

Same as above, but replace `magento/module-inventory-catalog-search-configurable-product` instead

### `Uncaught Error: Interface "Magento\QuoteGraphQl\Model\Cart\MergeCarts\CartQuantityValidatorInterface" not found in vendor/magento/module-inventory-quote-graph-ql/Model/Cart/MergeCarts/CartQuantityValidator.php:19`

Same as above, but replace `magento/module-inventory-quote-graph-ql` instead

### ` Uncaught Error: Interface "Magento\QuoteGraphQl\Model\Cart\Payment\AdditionalDataProviderInterface" not found in vendor/paypal/module-braintree-graph-ql/Model/BraintreeDataProvider.php:16`

Same as above, but replace `paypal/module-braintree-graph-ql` instead

### `Uncaught Error: Interface "Magento\GraphQl\Helper\Error\ExceptionMessageFormatterInterface" not found in vendor/magento/module-payment-graph-ql/Helper/Error/MessageFormatters/GatewayCommandExceptionMessageFormatter.php:21`

Same as above, but replace `magento/module-payment-graph-ql` instead

### `Uncaught Error: Class "Staempfli\ImageResizer\Model\Resizer" not found in app/code/VendorName/Downloads/Model/Resizer.php:17`

There is an undeclared dependency (`Staempfli\ImageResizer\Model\Resizer`) in the module `VendorName_Downloads`. In this case, `Staempfli\ImageResizer` is a module that has already been removed, hence the 'not found' error. 

The options are to composer replace `VendorName_Downloads`, or refactor `VendorName_Downloads` to remove the hidden dependency.

### Unable to apply data patch Magento\CatalogRuleSampleData\Setup\Patch\Data\InstallCatalogRuleSampleData for module Magento_CatalogRuleSampleData. Original exception message: Rolled back transaction has not been completed correctly. or Unable to apply data patch Magento\SalesRuleSampleData\Setup\Patch\Data\InstallSalesRuleSampleData for module Magento_SalesRuleSampleData. Original exception message: Rolled back transaction has not been completed correctly.

This happens because sample data in a CSV uses the wrong escaping method, triggering the error:

```
vendor/magento/module-catalog-rule-sample-data/fixtures/catalog_rules.csv
vendor/magento/module-sales-rule-sample-data/fixtures/sales_rules.csv
```

Either update the escaping method (to use `\"` rather than `""` to escape double-quotes) or just comment out the line so these particular scripts don't run.

Source: https://stackoverflow.com/questions/67923937/magento-2-4-unable-to-apply-data-patch-magento-catalogrulesampledata-setup-patc

### amasty_label view does not exist.

This is a problem with the extension not being installed properly.

Remove the entry from `setup_resource` in the database and try re-installing the module (enable the module and run setup:upgrade).

### class_alias(): Argument #1 ($class) must be a user-defined class name, internal class name given

Full error message:

```
...
  - Installing magento/inventory-composer-installer (1.2.0): Extracting archive
    Install of magento/inventory-composer-installer failed

In autoload.php line 13:
                                                                                                    
  [ValueError]                                                                                      
  class_alias(): Argument #1 ($class) must be a user-defined class name, internal class name given  
                                                                                                    

Exception trace:
  at /var/www/html/m2/research/m24-example-modules/html/vendor/laminas/laminas-servicemanager/src/autoload.php:13
 class_alias() at /var/www/html/m2/research/m24-example-modules/html/vendor/laminas/laminas-servicemanager/src/autoload.php:13
 require() at phar:///usr/local/bin/composer2/src/Composer/Autoload/AutoloadGenerator.php:1384
 Composer\Autoload\composerRequire() at phar:///usr/local/bin/composer2/src/Composer/Plugin/PluginManager.php:253
 Composer\Plugin\PluginManager->registerPackage() at phar:///usr/local/bin/composer2/src/Composer/Installer/PluginInstaller.php:85
 Composer\Installer\PluginInstaller->Composer\Installer\{closure}() at phar:///usr/local/bin/composer2/vendor/react/promise/src/FulfilledPromise.php:28
 React\Promise\FulfilledPromise->then() at phar:///usr/local/bin/composer2/vendor/react/promise/src/Promise.php:134
 React\Promise\Promise::React\Promise\{closure}() at phar:///usr/local/bin/composer2/vendor/react/promise/src/Promise.php:168
 React\Promise\Promise->settle() at phar:///usr/local/bin/composer2/vendor/react/promise/src/Promise.php:231
 React\Promise\Promise::React\Promise\{closure}() at phar:///usr/local/bin/composer2/vendor/react/promise/src/FulfilledPromise.php:42
 React\Promise\FulfilledPromise->done() at phar:///usr/local/bin/composer2/vendor/react/promise/src/Promise.php:135
 React\Promise\Promise::React\Promise\{closure}() at phar:///usr/local/bin/composer2/vendor/react/promise/src/Promise.php:168
 React\Promise\Promise->settle() at phar:///usr/local/bin/composer2/vendor/react/promise/src/Promise.php:231
 React\Promise\Promise::React\Promise\{closure}() at phar:///usr/local/bin/composer2/vendor/react/promise/src/FulfilledPromise.php:42
 React\Promise\FulfilledPromise->done() at phar:///usr/local/bin/composer2/vendor/react/promise/src/Promise.php:135
 React\Promise\Promise::React\Promise\{closure}() at phar:///usr/local/bin/composer2/vendor/react/promise/src/Promise.php:168
 React\Promise\Promise->settle() at phar:///usr/local/bin/composer2/vendor/react/promise/src/Promise.php:231
 React\Promise\Promise::React\Promise\{closure}() at phar:///usr/local/bin/composer2/vendor/react/promise/src/FulfilledPromise.php:42
 React\Promise\FulfilledPromise->done() at phar:///usr/local/bin/composer2/vendor/react/promise/src/Promise.php:135
 React\Promise\Promise::React\Promise\{closure}() at phar:///usr/local/bin/composer2/vendor/react/promise/src/Promise.php:168
 React\Promise\Promise->settle() at phar:///usr/local/bin/composer2/vendor/react/promise/src/Promise.php:231
 React\Promise\Promise::React\Promise\{closure}() at phar:///usr/local/bin/composer2/vendor/react/promise/src/FulfilledPromise.php:42
 React\Promise\FulfilledPromise->done() at phar:///usr/local/bin/composer2/vendor/react/promise/src/Promise.php:135
 React\Promise\Promise::React\Promise\{closure}() at phar:///usr/local/bin/composer2/vendor/react/promise/src/Promise.php:168
 React\Promise\Promise->settle() at phar:///usr/local/bin/composer2/vendor/react/promise/src/Promise.php:231
 React\Promise\Promise::React\Promise\{closure}() at n/a:n/a
 call_user_func() at phar:///usr/local/bin/composer2/src/Composer/Util/ProcessExecutor.php:321
 Composer\Util\ProcessExecutor->countActiveJobs() at phar:///usr/local/bin/composer2/src/Composer/Util/Loop.php:98
 Composer\Util\Loop->wait() at phar:///usr/local/bin/composer2/src/Composer/Installer/InstallationManager.php:506
 Composer\Installer\InstallationManager->waitOnPromises() at phar:///usr/local/bin/composer2/src/Composer/Installer/InstallationManager.php:479
 Composer\Installer\InstallationManager->executeBatch() at phar:///usr/local/bin/composer2/src/Composer/Installer/InstallationManager.php:390
 Composer\Installer\InstallationManager->downloadAndExecuteBatch() at phar:///usr/local/bin/composer2/src/Composer/Installer/InstallationManager.php:282
 Composer\Installer\InstallationManager->execute() at phar:///usr/local/bin/composer2/src/Composer/Installer.php:763
 Composer\Installer->doInstall() at phar:///usr/local/bin/composer2/src/Composer/Installer.php:590
 Composer\Installer->doUpdate() at phar:///usr/local/bin/composer2/src/Composer/Installer.php:279
 Composer\Installer->run() at phar:///usr/local/bin/composer2/src/Composer/Command/CreateProjectCommand.php:272
 Composer\Command\CreateProjectCommand->installProject() at phar:///usr/local/bin/composer2/src/Composer/Command/CreateProjectCommand.php:168
 Composer\Command\CreateProjectCommand->execute() at phar:///usr/local/bin/composer2/vendor/symfony/console/Command/Command.php:298
 Symfony\Component\Console\Command\Command->run() at phar:///usr/local/bin/composer2/vendor/symfony/console/Application.php:1024
 Symfony\Component\Console\Application->doRunCommand() at phar:///usr/local/bin/composer2/vendor/symfony/console/Application.php:299
 Symfony\Component\Console\Application->doRun() at phar:///usr/local/bin/composer2/src/Composer/Console/Application.php:335
 Composer\Console\Application->doRun() at phar:///usr/local/bin/composer2/vendor/symfony/console/Application.php:171
 Symfony\Component\Console\Application->run() at phar:///usr/local/bin/composer2/src/Composer/Console/Application.php:130
 Composer\Console\Application->run() at phar:///usr/local/bin/composer2/bin/composer:88
 require() at /usr/local/bin/composer2:29
```

This may occur when trying to install Magento using `composer create-project`, or performing any action which invokes the Composer autoloader (which is pretty much everything except the most basic of tasks).

Disable the PHP extension `psr`, if you have it enabled. It conflicts with the `laminas/laminas-servicemanager` dependency (Composer should raise a conflict, but not this time for some reason). 

Other debugging tips include:
- Verify you're using a supported version of PHP for that Magento version
- Verify you have `unzip` installed

The only other answer I could find was to downgrade from PHP8.1 to PHP7.4 (even though Magento 2.4.5 officially supports PHP8.1).

### Magento/PHP reports missing PHP extensions, even though they are present in phpinfo

Double-check that Magento is using the version of PHP you think it is. 

Tools may try running commands using `php`, defaulting to the latest installed version. If you're using any tools like PhpStorm, PhpUnit, n98-magerun etc, then try updating the 'default' version of PHP to the version you think it should be using, e.g:
```shell
sudo update-alternatives --config php
```
Then choose a version from the list that appears.

Source: https://serverok.in/set-default-php-version-in-ubuntu

### Feb 22 14:58:08 zone8-aurora-r5 nginx[28734]: nginx: [emerg] "fastcgi_busy_buffers_size" must be less than the size of all "fastcgi_buffers" minus one buffer in /etc/nginx/nginx.conf:58

Try removing the following from the `# PHP entry point for main application` location block:
```
#    fastcgi_buffers 16 16k;
#    fastcgi_buffer_size 32k;
```

### Notice: Undefined index: sections

When running the `setup:install` command:

```text

[Progress: 483 / 969]
Installing user configuration...

In ErrorHandler.php line 61:
                                                                                                                                                                           
  Notice: Undefined index: sections in /var/www/html/vendorname/projects/b-and-s/html/vendor/magento/module-config/Model/Config/Structure.php on line 235  
```

This was caused by the `sections.xml` file being in the wrong place. It should be in `etc/adminhtml/system.xml`.

### After 2.3.0 upgrade 'Zend\Mvc\Controller\LazyControllerAbstractFactory' not found

The issue can be fixed by manually editing composer.json autoload section to

```json
"autoload": {
    "psr-4": {
        "Magento\\Framework\\": "lib/internal/Magento/Framework/",
        "Magento\\Setup\\": "setup/src/Magento/Setup/",
        "Magento\\": "app/code/Magento/",
        "Zend\\Mvc\\Controller\\": "setup/src/Zend/Mvc/Controller/"
    },
    ...
```

and then run `composer dumpautoload`.

Source: https://github.com/magento/magento2/issues/15441

### Undefined offset: 2 in vendor/magento/framework/Encryption/Encryptor.php on line 588

You need to install the PHP `sodium` extension:

```
sudo apt install php7.1-sodium
sudo service php7.1-fpm restart
```

### Error during Magento 2 upgrade: “File doesn’t exist: bin/magento”

The `bin/magento` file is created by composer, so if it doesn't exist, it suggests composer hit a problem and didn't get that far. The problem is permissions, as hinted at in the error message with the mention of `chmod`:

```bash
File doesn't exist: bin/magento
Check "chmod" section in composer.json of magento/magento2-base package.
```

To diagnose, check the permissions of the `app/etc/` directory. The “magento” user will not have “write” permissions, but the “www-data” will. The permissions may also be set to `0575` in octal notation.

To fix, update the permissions of the `app/etc` directory to allow the “magento” user to have “write” permissions (i.e. `775`).

### Warning: call_user_func() expects parameter 1 to be a valid callback, class 'Vendor\Module\Setup\Patch\Data\DeleteInvalidCompanyAdvancedCustomerEntityRows' not found in /var/www/html/example-project/html/vendor/magento/framework/Setup/Patch/PatchRegistry.php on line 141

The class can't be autoloaded by PHP - check the namespace declaration in `Vendor\Module\Setup\Patch\Data\DeleteInvalidCompanyAdvancedCustomerEntityRows`.

###   [Magento\Framework\Setup\Exception] Unable to apply patch Vendor\ModuleName\Setup\Patch\Schema\MageplazaAttributesCleanup for module Vendor_ModuleName. Original exception message: Invalid entity_type specified: catalog_product

- Try adding `Magento_Catalog` to the dependency list in `module.xml`

### SQLSTATE[42S22]: Column not found: 1054 Unknown column 'e.customer_type' in 'field list'

```shell
Module 'Magento_Customer':
Running data recurring...
In Mysql.php line 110:

[Zend_Db_Statement_Exception (42)]
SQLSTATE[42S22]: Column not found: 1054 Unknown column 'e.customer_type' in 'field list', query was: SELECT `e`.`entity_id`, TRIM(CONCAT_WS(' ', IF(`e`.`prefix` <> '', `e`.`prefix`, NULL), IF(`e`.`firstname` <> '', `e`.`firstname`, NULL), IF(`e`.`middlename` <> '', `e`.`middlename`, NULL), IF(`e`.`lastname` <> '', `e`.`lastname`, NULL), IF(`e`.`suffix` <> '', `e`.`suffix`, NULL))) AS `name`, `e`.`email`, `e`.`group_id`, `e`.`created_at`, `e`.`website_id`, `e`.`confirmation`, `e`.`created_in`, `e`.`dob`, `e`.`gender`, `e`.`taxvat`, `e`.`lock_expires`, `e`.`customer_type`, TRIM(CONCAT_WS(' ', IF(`shipping`.`street` <> '', `shipping`.`street`, NULL), IF(`shipping`.`city` <> '', `shipping`.`city`, NULL), IF(`shipping`.`region` <> '', `shipping`.`region`, NULL), IF(`shipping`.`postcode` <> '', `shipping`.`postcode`, NULL))) AS `shipping_full`, TRIM(CONCAT_WS(' ', IF(`billing`.`street` <> '', `billing`.`street`, NULL), IF(`billing`.`city` <> '', `billing`.`city`, NULL), IF(`billing`.`region` <> '', `billing`.`region`, NULL), IF(`billing`.`postcode` <> '', `billing`.`postcode`, NULL))) AS `billing_full`, `billing`.`firstname` AS `billing_firstname`, `billing`.`lastname` AS `billing_lastname`, `billing`.`telephone` AS `billing_telephone`, `billing`.`postcode` AS `billing_postcode`, `billing`.`country_id` AS `billing_country_id`, `billing`.`region` AS `billing_region`, `billing`.`street` AS `billing_street`, `billing`.`city` AS `billing_city`, `billing`.`fax` AS `billing_fax`, `billing`.`vat_id` AS `billing_vat_id`, `billing`.`company` AS `billing_company` FROM `customer_entity` AS `e`
LEFT JOIN `customer_address_entity` AS `shipping` ON shipping.entity_id=e.default_shipping
LEFT JOIN `customer_address_entity` AS `billing` ON billing.entity_id=e.default_billing
```

There is something in the code trying to use the `customer_type` field from `Magento_Company`. Presumably the `Magento_Company` module is not enabled when the integration test runs. 

## Logging

### PHP Fatal error:  Uncaught Error: Class "Monolog\Logger" not found in ./vendor/monolog/monolog/src/Monolog/Handler/AbstractHandler.php:60

This occurred because the PHP PSR extension `php8.3-psr` was enabled, but is apparently 'broken' (see https://github.com/Seldaek/monolog/issues/1876#issuecomment-2031359811). Disabling the extension fixed the problem.

If that's not it, then try these steps:

Verify that the Monolog package is installed in ./vendor/monolog/monolog.

Try:
- Regenerate the autoloader: `composer dump-autoload -o`
- Reinstall monolog: `composer reinstall monolog/monolog`
- Reinstall Laravel: `composer reinstall laravel/laravel`
- Try upgrading or downgrading Monolog

## Upgrading

### `magento/magento2-functional-testing-framework[3.7.0, ..., 3.11.1] require guzzlehttp/guzzle ^7.3.0 -> found guzzlehttp/guzzle[7.3.0, ..., 7.5.0] but it conflicts with your root composer.json require (6.3.3).`

```
zone8@zone8-aurora-r5:$ php74 /usr/local/bin/composer2 require-commerce magento/product-community-edition 2.4.3 --no-update --force-root-updates --interactive-root-conflicts
PHP 7.4.32 (cli) (built: Oct 28 2022 18:18:05) ( NTS )
Copyright (c) The PHP Group
Zend Engine v3.4.0, Copyright (c) Zend Technologies
    with Zend OPcache v7.4.32, Copyright (c), by Zend Technologies
    with blackfire v1.84.0~linux-x64-non_zts74, https://blackfire.io, by Blackfire
Deprecation Notice: VersionSelector::findBestCandidate with ignored platform reqs as bool|array is deprecated since Composer 2.2, use an instance of PlatformRequirementFilterInterface instead. in phar:///usr/local/bin/composer2/src/Composer/Package/Version/VersionSelector.php:80
Deprecation Notice: VersionSelector::findBestCandidate with ignored platform reqs as bool|array is deprecated since Composer 2.2, use an instance of PlatformRequirementFilterInterface instead. in phar:///usr/local/bin/composer2/src/Composer/Package/Version/VersionSelector.php:80
Running native execute...
./composer.json has been updated

zone8@zone8-aurora-r5:$ php74 /usr/local/bin/composer2 update
PHP 7.4.32 (cli) (built: Oct 28 2022 18:18:05) ( NTS )
Copyright (c) The PHP Group
Zend Engine v3.4.0, Copyright (c) Zend Technologies
    with Zend OPcache v7.4.32, Copyright (c), by Zend Technologies
    with blackfire v1.84.0~linux-x64-non_zts74, https://blackfire.io, by Blackfire
Gathering patches for root package.
Loading composer repositories with package information
Info from https://repo.packagist.org: #StandWithUkraine
In Laminas\DependencyPlugin\DependencyRewriterV2::onPrePoolCreate
Updating dependencies
Your requirements could not be resolved to an installable set of packages.

  Problem 1
    - magento/magento2-functional-testing-framework[3.7.0, ..., 3.11.1] require guzzlehttp/guzzle ^7.3.0 -> found guzzlehttp/guzzle[7.3.0, ..., 7.5.0] but it conflicts with your root composer.json require (6.3.3).
    - Root composer.json requires magento/magento2-functional-testing-framework ^3.7 -> satisfiable by magento/magento2-functional-testing-framework[3.7.0, ..., 3.11.1].

Use the option --with-all-dependencies (-W) to allow upgrades, downgrades and removals for packages currently locked to specific versions.
```

Check to see if the dependency `guzzlehttp/guzzle` is defined in the root `composer.json` with a fixed dependency:

```json
{
    // ...
    "require": {
        "guzzlehttp/guzzle": "6.3.3",
        // ...
    }
}
```

If so, update the version constraint to a dynamic version constraint, then re-run the command:
```json
{
    // ...
    "require": {
        "guzzlehttp/guzzle": "^7.3"
        // ...
    }
}
```

## Admin

### Call to a member function getPart() on null: Exception in /var/www/html/wearemagneto/projects/feed-importer/html/vendor/magento/framework/View/Element/UiComponent/DataProvider/FilterPool.php:45

This happens when trying to load a custom grid in the admin. The root cause is that the collection class has not been initialised properly.

To fix it, verify that the collection that gets passed to the DataProvider has the `parent::__construct` call in its constructor.

In the `di.xml`:
```xml
<?xml version="1.0"?>
<config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:ObjectManager/etc/config.xsd">
    <type name="Magento\Framework\View\Element\UiComponent\DataProvider\CollectionFactory">
        <arguments>
            <argument name="collections" xsi:type="array">
                <!-- Find this collection class -->
                <item name="product_label_listing_data_source" xsi:type="string">ProcessEight\ProductLabel\Model\ResourceModel\Label\Grid\Collection</item>
            </argument>
        </arguments>
    </type>
</config>
```
In the collection class:
```php
namespace ProcessEight\ProductLabel\Model\ResourceModel\Label\Grid;

class Collection implements SearchResultInterface
{
    public function __construct(
        EntityFactoryInterface $entityFactory,
        LoggerInterface        $logger,
        FetchStrategyInterface $fetchStrategy,
        ManagerInterface       $eventManager,
        $model = Document::class,
        $connection = null,
        $resource = null
    ) {
        // Make sure the parent constructor is called:
        parent::__construct($entityFactory, $logger, $fetchStrategy, $eventManager, $connection, $resource);
        $this->_eventPrefix = 'product_label_grid_collection';
        $this->_eventObject = 'product_label_collection';
        
        // etc...
    }
}
```

### TypeError: Unsupported operand types: string - string in vendor/magento/module-catalog/Model/ResourceModel/Category.php:466

This appears to be a Magento bug - The position field in the 'Products in category' grid allows a non-integer value to be entered. The logic which determines whether the position has been updated does not validate the input and just assumes it is an integer, hence the problem.

### Warning: Undefined array key "id" in vendor/magento/module-config/Model/Config/Structure/Element/Iterator.php on line 63

This is caused by a custom module which is trying to add a new section to the admin configuration. The section references a tab that doesn't exist, or is in a disabled module.

The fix is to enable the module which defines the original tab, or remove the reference to the tab from the section.

This has happened when installing the MSP_DevTools 1.2.17 module on a Magento 2.4.5-p3 instance. In that instance, the `MSP_DevTools` module's section.xml file referenced a tab that was defined in the `MSP_Common` module, which was disabled.

See https://magento.stackexchange.com/a/213076

### Warning: Undefined array key "link_type" in /var/www/html/releases/42/vendor/magento/module-catalog/Model/ProductLink/ProductLinkQuery.php on line 177

The problem was tracked down to an overridden class `\VendorName\Catalog\Model\ProductLink\CollectionProvider` which extends and overrides `\Magento\Catalog\Model\ProductLink\CollectionProvider` by means of an adminhtml `di.xml` `preference`.

The class was overridden to modify the logic of `\Magento\Catalog\Model\ProductLink\CollectionProvider::getCollection`.

That method calls `\Magento\Catalog\Model\ProductLink\CollectionProvider::prepareList`, which returns a multidimensional array of linked product metadata, which includes the `link_type` array element.

The overridden class does not call `\Magento\Catalog\Model\ProductLink\CollectionProvider::prepareList` and therefore the `link_type` array element never gets added to the array of sorted linked products returned by `\VendorName\Catalog\Model\ProductLink\CollectionProvider::getCollection`.

The solution is to add the `link_type` to that array in the overridden class.

### 'Invalid form key. Please refresh the page' when trying to save products

This may only affect certain products.

Try increasing the `max_input_vars` PHP INI value to something greater than the default (1000).

Alternately, check for any ajax requests executing in the background, especially ones from custom modules. Poorly written requests which aren't defined in the adminhtml area or don't implement the proper ACL checks may be redirected by Magento to the login URL, thus invalidating the form key for the session. 

### Error in data structure: entity values are mixed

This error stemmed from the fact the module FireGento_FastSimpleImport2 was installed and has an option to use a MySQL temporary table when importing, rather than using the default one (`importexport_importdata`). 

This option is enabled by default. Disabling it in the config solved the issue.

### Class Magento\Logging\Model\Source\Frequency does not exist

When trying to access the Stores, Configuration of an extension, this error message appears.

Searching for the class in the codebase reveals this definition in a `system.xml` file:

```xml
                    <source_model>Magento\Logging\Model\Source\Frequency</source_model>
```

This module (Magento Logging) seems not to be available in Magento 2 CE 2.3.5-p2.

It appears this module is only available in EE. Its purpose is to assist in Admin user actions logging.

The answer is to copy the source model into a custom source model class. The Magento class is exceedingly simple anyway:

```php
<?php
/**
 * Copyright © Magento, Inc. All rights reserved.
 * See COPYING.txt for license details.
 */

namespace Magento\Logging\Model\Source;

/**
 * Source model for logging frequency
 *
 * @api
 * @since 100.0.2
 */
class Frequency implements \Magento\Framework\Option\ArrayInterface
{
    /**
     * Get options as array
     *
     * @return array
     */
    public function toOptionArray()
    {
        return [
            ['value' => 1, 'label' => __('Daily')],
            ['value' => 7, 'label' => __('Weekly')],
            ['value' => 30, 'label' => __('Monthly')]
        ];
    }
}
```

### MySQL adapter: Missing required configuration option 'host'

The usual solutions:

See https://stackoverflow.com/a/64444565 and https://stackoverflow.com/a/69534967

However, the stack trace of my error revealed something else:

```
MySQL adapter: Missing required configuration option 'host':
#1 FishPig\\WordPress\\App\\Integration\\Tests\\Proxy->runTests() called at [vendor/fishpig/magento2-wordpress-integration/App/View/AssetProvider.php:68]
#2 FishPig\\WordPress\\App\\View\\AssetProvider->provideAssets() called at [vendor/fishpig/magento2-wordpress-integration/Plugin/Magento/Framework/Controller/ResultPlugin.php:36]
#3 FishPig\\WordPress\\Plugin\\Magento\\Framework\\Controller\\ResultPlugin->afterRenderResult() called at [vendor/magento/framework/Interception/Interceptor.php:146]
#4 Magento\\Framework\\View\\Result\\Page\\Interceptor->Magento\\Framework\\Interception\\{closure}() called at [vendor/magento/framework/Interception/Interceptor.php:153]
#5 Magento\\Framework\\View\\Result\\Page\\Interceptor->___callPlugins() called at [generated/code/Magento/Framework/View/Result/Page/Interceptor.php:95]
#6 Magento\\Framework\\View\\Result\\Page\\Interceptor->renderResult() called at [vendor/magento/framework/App/Http.php:120]
#7 Magento\\Framework\\App\\Http->launch() called at [generated/code/Magento/Framework/App/Http/Interceptor.php:23]
#8 Magento\\Framework\\App\\Http\\Interceptor->launch() called at [vendor/magento/framework/App/Bootstrap.php:264]
#9 Magento\\Framework\\App\\Bootstrap->run() called at [pub/index.php:29]
```

This happened because the 'Integration mode' was set to 'External', but there were no connection details to the 'external' database configured in `core_config_data`. Switching the `FishPig_WordPress` integration mode to 'Local' fixed the problem.

### Notice: SessionHandler::gc(): ps_files_cleanup_dir: opendir(/var/lib/php/sessions) failed: Permission denied

```
1 exception(s):
Exception #0 (Exception): Notice: SessionHandler::gc(): ps_files_cleanup_dir: opendir(/var/lib/php/sessions) failed: Permission denied (13) in vendor/magento/framework/Session/SaveHandler.php on line 212
```

### Class argument is invalid: Magento\Framework\View\Element\UiComponent\Context

The 'invalid' class argument needs to be added to a whitelist.

For example the argument named 'class' in this example:

```xml
// html/app/code/VendorName/ModuleName/view/adminhtml/ui_component/modulename_log_listing.xml
<?xml version="1.0"?>
<listing xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
         xsi:noNamespaceSchemaLocation="urn:magento:module:Magento_Ui:etc/ui_configuration.xsd">
    <argument name="context" xsi:type="configurableObject">
        <argument name="class" xsi:type="string">Magento\Framework\View\Element\UiComponent\Context</argument>
        <argument name="namespace" xsi:type="string">modulename_log_listing</argument>
    </argument>
    ...
```

Needs to be whitelisted as so:

```xml
<?xml version="1.0"?>
<config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:noNamespaceSchemaLocation="urn:magento:framework:ObjectManager/etc/config.xsd">
    <type name="Magento\Framework\View\Element\UiComponent\Argument\Interpreter\ConfigurableObject">
        <arguments>
            <argument name="classWhitelist" xsi:type="array">
                <item name="2" xsi:type="string">Magento\Framework\View\Element\UiComponent\ContextInterface</item>
                // ...
            </argument>
        </arguments>
    </type>
</config>
```

An odd thing I noticed is that whilst whitelisting the matching interface works for arguments passed to the `listing` element, doing the same thing for arguments passed to the `dataSource` element still produces the same error:

```xml
// html/app/code/VendorName/ModuleName/view/adminhtml/ui_component/modulename_log_listing.xml
    <dataSource name="modulename_log_listing_data_source">
        <argument name="dataProvider" xsi:type="configurableObject">
            <argument name="class" xsi:type="string">Magento\Framework\View\Element\UiComponent\DataProvider\DataProvider</argument>
```



```xml
<?xml version="1.0"?>
<config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:noNamespaceSchemaLocation="urn:magento:framework:ObjectManager/etc/config.xsd">
    <type name="Magento\Framework\View\Element\UiComponent\Argument\Interpreter\ConfigurableObject">
        <arguments>
            <argument name="classWhitelist" xsi:type="array">
                <item name="2" xsi:type="string">Magento\Framework\View\Element\UiComponent\ContextInterface</item>
                // This still produces the error
                <item name="4" xsi:type="string">Magento\Framework\View\Element\UiComponent\DataProvider\DataProviderInterface</item>
                // This does not. No idea why we need to pass a concrete instance here whilst argument `2` accepts an interface.
                <item name="4" xsi:type="string">Magento\Framework\View\Element\UiComponent\DataProvider\DataProvider</item>
            </argument>
        </arguments>
    </type>
</config>
```

### Something went wrong with reCAPTCHA. Please contact the store owner.

This turned out to be a FireFox on Ubuntu 18.04.6 LTS issue. It doesn't occur on FireFox/Mac OSX Catalina 10.15.7 

Make sure you only have one CAPTCHA module enabled. They may conflict with one another. Common ones include MSP_ReCaptcha (which was merged into Magento 2 core in 2.4x), Google's own reCAPTCHA module and the Magento 2 core module (which generates its own CAPTCHA images).

- Try unlocking the admin user
- Clear cache

### Default Product Listing Sort by does not exist in Available Product Listing Sort By.

It appears Magento does not like using the 'Default Product Listing Sort by' value of 'Position', even if it is explicitly selected as one of the 'Available Product Listing Sort By' values. This will happen if `Use Config Settings` is checked for `Default Product Listing Sort By`.

A workaround is to uncheck `Use Config Settings` for `Default Product Listing Sort By` and instead explicitly select it, as well as explicitly selecting 'Position' as one of the 'Available Product Listing Sort By' values.

### Fatal error: Cannot declare class Zend_Http_Client, because the name is already in use in .../vendor/magento/zendframework1/library/Zend/Http/Client.php on line 72

Try upgrading the installed version of `klevu/module-search` from 2.6 to 3.1.x.

### Uncaught ReflectionException: Class Magento\Framework\App\ResourceConnection\Proxy does not exist in /var/www/html/m2/research/m24-example-modules/html/vendor/magento/framework/Code/Reader/ClassReader.php:34

A core class is missing. Verify that Magento is installed correctly. Re-run the composer install command to ensure all core files have been installed. 

### Fatal error: Uncaught TypeError: Argument 2 passed to Magento\Framework\View\Element\UiComponentFactory::argumentsResolver() must be of the type array, null given, called in ../vendor/magento/framework/View/Element/UiComponentFactory.php on line 208 and defined in ../vendor/magento/framework/View/Element/UiComponentFactory.php:174

The page is trying to load a UI Component, which has not been configured correctly. Verify that the name of the ui_component in the Layout XML matches the filename of the UI component XML file.

### UI Component not working properly

Confirm that the initialize method of your component contains the call to `this._super()`:

```javascript
    return Component.extend({
        initialize: function () {
            // Just like in PHP, _super() calls the parent method.
            // This UI Component extends the Component class, which extends the Element class.
            // There is no initialize() method in the Component class, so it calls the Element class's initialize() method.
            // The parent's initialize() method is defined in vendor/magento/module-ui/view/base/web/js/lib/core/element/element.js:102
            this._super();
            
            // Other logic goes here
        }
```

### jQuery.Deferred exception: Unable to process binding "text: function(){return messageDefault }": Message: messageDefault is not defined text@http://m24-example-modules.local/static/version1711997660/frontend/Magento/luma/en_GB/knockoutjs/knockout.js line 3221 > Function:3:57

This error occurs when a UI Component is trying to bind to a non-existent property.

If you've recently added or renamed a property of a UI Component in a layout XML file, clear the config cache first.

Then make sure the property is defined in the UI Component itself. For example, if the property `message` is defined in the layout XML file, make sure it is also defined in the UI Component JS file:

```xml  
<!-- File: view/frontend/layout/default.xml -->
    <item name="free-shipping-banner" xsi:type="array">
        <item name="config" xsi:type="array">
            <item name="message" xsi:type="string">This is a custom property! Also, Free Shipping on Orders Over $50!</item>
        </item>
    </item>
```

```javascript
// File: view/frontend/web/js/free-shipping-banner.js
define([
    'uiComponent'
], function (
    Component
) {
    'use strict';

    return Component.extend({
        defaults: {
            message: 'This is a custom property! Also, Free Shipping on Orders Over $50!',
        }
    });
});
```


Make sure that a `data-bind` attribute exists which binds the UI Component (`free-shipping-banner`) to the DOM element (`#free-shipping-banner`), and that the property `message` is defined in the UI Component JS file:

```html
<div id="free-shipping-banner" data-bind="scope: 'free-shipping-banner'">
    <div data-bind="text: message"></div>
</div>
<script type="text/x-magento-init">
    {
        "#free-shipping-banner": {
            "Magento_Ui/js/core/app": <?= /* @noEscape */ $block->getJsLayout() ?>
        }
    }
</script>
```
The 'message' property is defined in the UI Component JS file:
```javascript
define([
    'uiComponent'
], function (
    Component
) {
    'use strict';

    return Component.extend({
        defaults: {
            message: 'This is a custom property! Also, Free Shipping on Orders Over $50!',
```

### JS Objects (including UI Components) are sometimes empty, sometimes not

This is most likely caused by the data being returned by a method which uses promises. If the object is being returned before the promise resolves, the object will be empty.

An example of this is with the `customerData` UI Component. There might be instances where calling `customerData.get('cart') results in the cart data sometimes being retrieved and sometimes not. In this instance, in the customer-data.js file, we find a function called `getInitCustomerData`. It checks if customer data is initialised and returns a promise. We can use this to ensure that the cart data is always available:

```javascript
define([
    'uiComponent',
    'Magento_Customer/js/customer-data'
], function (
    Component, customerData
) {
    'use strict';

    return Component.extend({
        initialize: function () {
            this._super();

            let cart = customerData.get('cart');
            customerData.getInitCustomerData().done(function () {
                // This will only execute when the promise resolves and therefore cart data is definitely available
                console.log('Cart data:', cart());
            });
        }
    });
});
```

In our UI Component, after the call to get the cart, make a call to customerData.getInitCustomerData(), and then call done. This function accepts a callback, which will only execute when the promise resolves. Move the call to the console within this function callback.

###  Uncaught ReferenceError: Component is not defined

```shell
 Uncaught ReferenceError: Component is not defined
    <anonymous> http://m24-example-modules.local/static/version1711997660/frontend/Magento/luma/en_GB/Macademy_CheckoutMessages/js/view/summary/cart-items-mixin.js:5
```

Mixins always have to return a function. Verify that your mixin is returning a function:

```javascript
define([], function () {
    'use strict';

    // Component is the UI Component that the mixin is being applied to, e.g. 'Magento_Checkout/js/view/summary/cart-items'
    return function (Component) {
        return Component.extend({
            // Your mixin logic goes here
            // e.g. Force the 'Order Summary' block in the checkout to be expanded by default
            isItemsBlockExpanded: function () {
                return true;
            }
        });
    };
});
```

### Trying to load example.com/admin produces 404

Verify if `admin` is the correct front name for the admin panel. The front name is defined in `env.php`:
```php
return [
    'backend' => [
        'frontName' => 'admin'
    ],
```

Also check `core_config_data` in the database for these paths: `admin/url/custom_path` and `admin/url/use_custom_path`.

### Call to undefined method ProcessEight\LayeredNavCustomSeo\Model\CrawlableRepository::create() in /var/www/html/m2/research/m23-example-modules/html/app/code/ProcessEight/LayeredNavCustomSeo/Plugin/Eav/Block/Adminhtml/Attribute/Edit/Options/OptionsPlugin.php

This is because you are trying to use the dependency as a factory (which defines the `create` method), but you have not injected it as a factory. The factory class is not generated and therefore the `create` method does not exist either. 

For example, in this constructor, the class properties have the keyword `Factory` appended, but the class name does not - but it's the class name that counts. So, `\ProcessEight\LayeredNavCustomSeo\Api\CrawlableRepositoryInterface` needs to have the keyword `Factory` appended to it: `\ProcessEight\LayeredNavCustomSeo\Api\CrawlableRepositoryInterfaceFactory`.

```php
/**
 * Constructor.
 *
 * @param \ProcessEight\LayeredNavCustomSeo\Api\CrawlableRepositoryInterface $crawlableRepositoryFactory
 */
public function __construct(
    // Incorrect:
    \ProcessEight\LayeredNavCustomSeo\Api\CrawlableRepositoryInterface $incorrectRepositoryFactory
    // Correct:
    \ProcessEight\LayeredNavCustomSeo\Api\CrawlableRepositoryInterfaceFactory $correctRepositoryFactory
) {
    $this->incorrectRepositoryFactory = $incorrectRepositoryFactory;
    $this->correctRepositoryFactory = $correctRepositoryFactory;
}
```

### Could not create an acl object: Invalid Document

When you login to the admin, you get an error message like this one:
```
Exception #0 (LogicException): Could not create an acl object: Invalid Document 
Element 'resource': The attribute 'title' is required but missing.
Line: 7
```
The solution is simple - find the offending `resource` node and add the missing `title` attribute. Finding the module in the mountain of XML used by Magento 2 will be harder said than done though. One way would be to progressively disable third-party modules (including bundled ones) until the error disappears.

### Cannot login to admin: 'Too many redirects'

This is a cookie issue. Make sure your cookie domain matches the URL of the website:
```bash
example_db> select * from core_config_data where path like '%cookie%' order by scope, scope_id, path
+-----------+---------+----------+-------------------------------------------------+-----------------------------------------+
| config_id | scope   | scope_id | path                                            | value                                   |
+-----------+---------+----------+-------------------------------------------------+-----------------------------------------+
| 226       | default | 0        | web/cookie/cookie_domain                        | http://www.example.local/ |
| 227       | default | 0        | web/cookie/cookie_httponly                      | 1                                       |
| 225       | default | 0        | web/cookie/cookie_path                          | /                                       |
+-----------+---------+----------+-------------------------------------------------+-----------------------------------------+

```
The above settings should allow you to login to `http://www.example.local/admin/`.

### Exception #0 (Magento\Framework\Exception\RuntimeException): Type Error occurred when creating object: Trespass\ApproveSuspectedFraudOrders\Controller\Adminhtml\Payment\Approve\Interceptor

An invalid dependency may have been defined in a class constructor.
 
 * Check for typos, casing and correct namespace in any recently added or modified dependencies.
 
 This may also happen when a `parent::__construct($context);` call is missing from an overridden constructor (in this case, the error will come from the parent constructor of the extending class, rather than the overridden constructor itself).


### DateTime::__construct(): Failed to parse time string (19/10/2018 00:00) at position 0 (1): Unexpected character
* Workaround: Inject the values directly into the database:
```mysql
mysql> select * from catalog_product_entity_varchar where entity_id = 14235;
mysql> insert into catalog_product_entity_varchar set attribute_id=95, store_id=0, entity_id=14235, value='2018-11-19 14:35';
mysql> insert into catalog_product_entity_varchar set attribute_id=94, store_id=0, entity_id=14235, value='2018-12-19 15:35';
```

### 'PHP Notice in magento 2.2: Notice: Undefined index: id in vendor/magento/module-config/Model/Config/Structure/Element/Iterator.php on line 63' when trying to access Stores > Configuration in M2.2
* This is caused by having an in invalid install of the MSP_DevTools extension. Remove and re-install it to fix the error.

### 'The value of attribute "..." must be set' when adding a new customer attribute
* The attribute has not been added to the `customer_form_attribute` table. Magento uses this table to get all the attributes that need validating in specific forms. Add an entry for the affected attribute to this table.

### Styles appear in frontend and on admin login page, but not in admin panel after logging in
* Ensure that the `Magento/backend` theme has been deployed with the locale code `en_US`:
```bash
# Deploys the default admin theme only
$ bin/magento setup:static-content:deploy en_US --theme Magento/backend
```

### PHP Fatal error: 'Cannot declare class because the name is already in use'
```bash
PHP Fatal error: Cannot declare class ProjectEight\AddNewApiMethod\Api\Calculator, because the name is already in use in /var/www/vhosts/magento2-sample-modules.localhost.com/app/code/ProjectEight/AddNewApiMethod/Model/Calculator.php on line 20
```
You have an incorrect (or missing) namespace definition. Double-check your `namespace` definitions and `use` statements.

### Exception #0 (ReflectionException): Class Magento\Framework\View\Element\UiComponent\DataProvider\DataProvider does not exist
```bash
Exception: Exception #0 (ReflectionException): Class Magento\Framework\View\Element\UiComponent\DataProvider\DataProvider
             does not exist
```
Note how the exception message peculiarly wraps onto two lines. Double-check your UI component XML files (located in `app/code/<vendor_name>/<module_name>/view/adminhtml/ui_component/<layout_handle>.xml`). Make sure that where the `Magento\Framework\View\Element\UiComponent\DataProvider\DataProvider` is defined there is no trailing whitespace within the tags, especially if you have used the Re-format code tool in PhpStorm.

### Call to undefined method Magento\Framework\Controller\Result\Forward\Interceptor::create() in /var/www/vhosts/m2-example-modules.localhost.com/app/code/ProjectEight/PersistenceLayerExample/Controller/Adminhtml/WhatsIt/NewAction.php:49
* Make sure you're passing a factory class and not a model in the constructor for `NewAction`
* Run `$ bin/magento setup:upgrade` afterwards

### Uncaught TypeError: Argument 5 passed to ProjectEight\PersistenceLayerExample\Controller\Adminhtml\WhatsIt::__construct() must be an instance of Magento\Backend\Model\View\Result\ForwardFactory, none given, called in /var/www/vhosts/m2-example-modules.localhost.com/var/generation/ProjectEight/PersistenceLayerExample/Controller/Adminhtml/WhatsIt/Edit/Interceptor.php on line 14 and defined in /var/www/vhosts/m2-example-modules.localhost.com/app/code/ProjectEight/PersistenceLayerExample/Controller/Adminhtml/WhatsIt.php:54
* This usually happens after editing the constructor of a class
* Run `$ bin/magento setup:upgrade` to update the DI dependency tree

### Not registered handle
Magento can't find the collection used for your data source. Verify your data source is defined correctly in the `di.xml` and `ui_component` XML files:

`app/code/ProjectEight/PersistenceLayerExample/view/adminhtml/ui_component/projecteight_whatsit_index.xml`
```xml<?xml version="1.0" encoding="UTF-8"?>
<listing xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:module:Magento_Ui:etc/ui_configuration.xsd">
    <!-- The dataSource name is what we use to reference the grid in the di.xml -->
    <dataSource name="projecteight_whatsit_index_data_source">
        <argument name="dataProvider" xsi:type="configurableObject">
            <argument name="class" xsi:type="string">Magento\Framework\View\Element\UiComponent\DataProvider\DataProvider</argument>
            <argument name="name" xsi:type="string">projecteight_whatsit_index_data_source</argument>
            <argument name="primaryFieldName" xsi:type="string">whatsit_id</argument>
            <argument name="requestFieldName" xsi:type="string">id</argument>
            <argument name="data" xsi:type="array">
                <item name="config" xsi:type="array">
                    <item name="component" xsi:type="string">Magento_Ui/js/grid/provider</item>
                    <item name="update_url" xsi:type="url" path="mui/index/render"/>
                </item>
            </argument>
        </argument>
    </dataSource>
</listing>
```

`app/code/ProjectEight/PersistenceLayerExample/etc/di.xml`
```xml
<?xml version="1.0" ?>
<config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:noNamespaceSchemaLocation="urn:magento:framework:ObjectManager/etc/config.xsd">
<type name="Magento\Framework\View\Element\UiComponent\DataProvider\CollectionFactory">
        <arguments>
            <argument name="collections" xsi:type="array">
                <!-- Note the item name is the name of the data source configured in the ui_component XML file -->
                <item name="projecteight_whatsit_index_data_source" xsi:type="string">ProjectEight\PersistenceLayerExample\Model\ResourceModel\WhatsIt\Grid\Collection</item>
            </argument>
        </arguments>
    </type>
</config>
```
See also https://magento.stackexchange.com/a/171226 for more details.

### Magento can generate files when invoked using `bin/magento setup:di:compile`, but not when invoked during code execution (i.e. Loading a page, running a (different) bin/magento command)

If the PHP process owner (apache or php-fpm) isn't allowed to write to `generated/code`, but the user that you run `bin/magento` as is allowed to, then this might be a permissions issue.

### Notice: Undefined offset: 2 in /www/web/demo/vendor/magento/framework/Encryption/Encryptor.php

From 2.3.2, Magento uses the Sodium cryptography library and updates the hashes of all passwords accordingly. This error refers to the fact that Magento has detected that the PHP sodium module is not loaded, but the hash is not in the SHA-256 format (which Magento uses as the fallback crytography library).

The solution is to ensure that PHP's sodium extension is enabled (it is enabled by default in 7.2+).

### Area code is not set

```html
<b>Fatal error</b>:  Uncaught Magento\Framework\Exception\LocalizedException: Area code is not set in /var/www/html/jacobs-turner/m23ee-trespass/html/vendor/magento/framework/App/State.php:153
```
If the above error appeared after navigating from a base URL (e.g. www.example.com) to a sub-domain hosting a store (e.g. www.example.com/uk), then it could be problem with the Nginx configuration, i.e. There is no configuration which tells Magento www.example.com/uk that there is a store there.

### Logged out when browsing the 'Edit Product' page

This happens because something is dispatching a request which does not have a proper form key set, or is outside the `adminhtml` area. This invalidates the session and Magento thus kicks you out.

This can happen to a specific product, without affecting other products. It is possible doing something like editing a category (or something else which involves interacting with any form field or UI Component more complicated than a text input) can trigger some logic to be lazy-loaded and executed, triggering the problem.

To fix, try reverting whatever was the last edit you made to a product. You may have to edit the product without the benefit of the Admin GUI.

Try loading a different product, then go back and load the problem product. This may be enough to clear/reset certain values stored in the session for the admin user you are logged in as.

### Exception #0 (Zend_Db_Statement_Exception): SQLSTATE[42S22]: Column not found: 1054 Unknown column '' in 'where clause', query was: SELECT COUNT(*) FROM moorelarge_feedprocessorbase_message AS main_table WHERE ('' IN('3', '4'))

This is due to the `\Magento\Framework\Data\Collection\AbstractDb::$_idFieldName` property not being set. When the collection is created using the `\Magento\Framework\View\Element\UiComponent\DataProvider\CollectionFactory`, it is set automatically, though if the collection used is created by using a generated factory class (e.g. `\MooreLarge\FeedProcessorBase\Model\ResourceModel\Message\CollectionFactory`), it doesn't seem to be set, hence the error.

The solution is to override the `_idFieldName` property and define it in the collection class:

```php
<?php 
declare(strict_types=1);
namespace Yourname\Modulename\Model\ResourceModel\Modelname;
use Magento\Framework\Model\ResourceModel\Db\Collection\AbstractCollection;
use Yourname\Modulename\Model\Faq;
class Collection extends AbstractCollection
{
    // This property must be explicitly defined
    // 'id' refers to the primary key of the table associated with this collection
    protected $_idFieldName = 'id';
    
    protected function _construct()
    {
        $this->_init(Modelname::class, \Yourname\Modulename\Model\ResourceModel\Modelname::class);
    }
}
```

## Elasticsearch

### {"error":{"root_cause":[{"type":"cluster_block_exception","reason":"blocked by: [FORBIDDEN/12/index read-only / allow delete (api)];"}],"type":"cluster_block_exception","reason":"blocked by: [FORBIDDEN/12/index read-only / allow delete (api)];"},"status":403}

This happens because you are probably running out of disk space and Elasticsearch turns itself into read only mode because, well, there's no more space to do stuff.

In order to get out of this situation, you need to first disable that Elasticsearch feature of switching to read only mode (otherwise it will happen again) by running the following...

```shell
curl -XPUT -H "Content-Type: application/json" http://localhost:9200/_cluster/settings -d '{"persistent":{"cluster.routing.allocation.disk.threshold_enabled":false}}'
```

...and then get Elasticsearch out of the read only mode with the next command:

```shell
curl -XPUT -H "Content-Type: application/json" http://localhost:9200/_all/_settings -d '{"index.blocks.read_only_allow_delete": null}'
```

Besides this, you'll need to do some disk clean up to recover some space.

Source: https://www.naguel.com/blocked-by-forbidden-12-index-read-only-allow-delete-api/


### Elasticsearch totally fails to start

It may sound obvious, but verify you have Java installed. 

The `sudo apt autoremove` command may have removed Java because it believes it is no longer being used.

For Ubuntu 16, the right version is:
```bash
$ /usr/bin/java -version
openjdk version "1.8.0_242"
OpenJDK Runtime Environment (build 1.8.0_242-8u242-b08-0ubuntu3~16.04-b08)
OpenJDK 64-Bit Server VM (build 25.242-b08, mixed mode)
```
Install it thusly:
```bash
$ sudo apt install openjdk-8-jre-headless
```

For Ubuntu 18, the right version is:
```bash
$ /usr/bin/java -version
openjdk version "11.0.6" 2020-01-14
OpenJDK Runtime Environment (build 11.0.6+10-post-Ubuntu-1ubuntu118.04.1)
OpenJDK 64-Bit Server VM (build 11.0.6+10-post-Ubuntu-1ubuntu118.04.1, mixed mode, sharing)
```
Install it thusly:
```bash
$ sudo apt install default-jre default-jdk
```

### Cannot start Elasticsearch; Elasticsearch starts but fails almost immediately

If Elasticsearch has been upgraded recently (or if you've run `sudo apt update` recently), try upgrading any plugins. Upgrading ES does not automatically upgrade it's plugins as well.

To upgrade the plugins required by Magento 2:

```bash
cd /usr/share/elasticsearch
bin/elasticsearch-plugin install analysis-phonetic
sudo bin/elasticsearch-plugin remove analysis-icu
sudo bin/elasticsearch-plugin install analysis-icu
sudo bin/elasticsearch-plugin remove analysis-phonetic
sudo bin/elasticsearch-plugin install analysis-phonetic
sudo service elasticsearch restart
```

### Cannot save stock items or products, e.g. The stock item was unable to be saved

If the catalog search engine is set to `Elasticsearch`, make sure it is running. Visit http://localhost:9200/ to check.

As of 2.3.1, Elasticsearch is the default search engine. If Elasticsearch is not setup, this can cause fatal errors when Magento tries to update stock items.

Try switching back to MySQL in Admin, Stores, Configuration, Catalog, Catalog, Catalog Search, Search Engine.

Note that MySQL has been deprecated as a search engine, so this is only a short-term fix.

To fix it, just set `fulltext` as the default search engine (from 2.3.1 onwards):

```mysql
update core_config_data set value = 'fulltext' where path = 'catalog/search/engine'
```

Note that MySQL was removed as a search engine option in 2.4

Another solution is to switch indexers to 'Update on Schedule'. I don't know why that works though.

Also try the usual, `cache:flush` and `indexer:reindex`.

### Exception #0 (Elasticsearch\Common\Exceptions\NoNodesAvailableException): No alive nodes found in your cluster

If the catalog search engine is set to `Elasticsearch`, make sure it is running. Visit http://localhost:9200/ to check.

As of 2.3.1, Elasticsearch is the default search engine. If Elasticsearch is not setup, this can cause fatal errors when Magento tries to update stock items.

Try switching back to MySQL in Admin, Stores, Configuration, Catalog, Catalog, Catalog Search, Search Engine.

Note that MySQL has been deprecated as a search engine, so this is only a short-term fix.

To fix it, just set `fulltext` as the default search engine (from 2.3.1 onwards):

```mysql
update core_config_data set value = 'fulltext' where path = 'catalog/search/engine'
```

The problem is the same as the one above. This would most likely have happened after importing a backup of a staging/production database into an environment (e.g. local) without Elasticsearch running.

Try re-indexing everything:
```bash
mr23 ind:reset && mr23 ind:rei
```

If that doesn't work, try rebooting the machine.

### Elasticsearch is running, but cannot connect to http://localhost:9200/

If the catalog search engine is set to `Elasticsearch`, make sure it is running. Visit http://localhost:9200/ to check.

If that doesn't work, try restarting ES.

If that doesn't work, try explicitly setting the `network.host` value to `127.0.0.1` in `/etc/elasticsearch/elasticsearch.yml`.

Try re-indexing everything:
```bash
mr23 ind:reset && mr23 ind:rei
```

If that doesn't work, try rebooting the machine.

### Elasticsearch is running, but cannot create `catalog_product` index

If the catalog search engine is set to `Elasticsearch`, make sure it is running. Visit http://localhost:9200/ to check.

If that doesn't work, try deleting all the Smile Elasticsearch modules from `setup_modules` and then run `bin/magento setup:upgrade` and try re-indexing again.

Try re-indexing everything:
```bash
mr23 ind:reset && mr23 ind:rei
```

If that doesn't work, try rebooting the machine.

### Catalog Search indexer process unknown error: Indexer handler is not available: elasticsuite

```bash
$ date && php73 -f bin/magento ind:rei catalogsearch_fulltext && dateDo 16. Jul 13:52:44 BST 2020
PHP 7.3.19-1+ubuntu16.04.1+deb.sury.org+1 (cli) (built: Jun 12 2020 07:48:10) ( NTS )
Copyright (c) 1997-2018 The PHP Group
Zend Engine v3.3.19, Copyright (c) 1998-2018 Zend Technologies
    with Zend OPcache v7.3.19-1+ubuntu16.04.1+deb.sury.org+1, Copyright (c) 1999-2018, by Zend Technologies
Catalog Search indexer process unknown error:
Indexer handler is not available: elasticsuite
```

If the catalog search engine is set to `Elasticsearch`, make sure it is running. Visit http://localhost:9200/ to check.

If that doesn't work, try restarting ES.

### General debugging tips for Elasticsearch

- Does the alias in the config match the alias used in ES for it's indexes?
- Try querying ES directly to see if there are any products indexed in ES:
```bash
$ curl -X GET http://127.0.0.1:9200/_cat/indices/
green open magento2_stg_product_5_v591 s9aoJs3hQQ-Ucsnn8fJObg 3 2  2596  0  6.1mb    2mb
green open magento2_stg_product_1_v567 sk_pVcKoSUqZtWBHBRwK1A 3 2 13385  0 23.2mb  7.6mb
green open magento2_product_5_v456     YXOUzYSHSWuFKj_CjhcLUA 3 2  3126  7  5.1mb  1.7mb
green open magento2_stg_product_2_v591 mGwg8RQdTUCb3DT5sx9NrA 3 2     1  0 34.4kb 11.4kb
green open magento2_stg_product_4_v591 bjfDoFmZTkiPYoING43Cng 3 2 13385  0 23.9mb  8.3mb
green open magento2_product_2_v456     _Kh36j09ThS8Hab2FC4vZw 3 2     1  0 41.1kb 13.7kb
green open magento2_product_4_v456     Awwv-b8TQRed0hPimm9gBw 3 2 14398 19 34.2mb  7.8mb
green open magento2_product_1_v456     BG9OUNMKTMajcRwB1ElSNA 3 2 14398 11   29mb 13.2mb
```

- Try querying the health status of ES:
```bash
$ curl -X GET "127.0.0.1:9200/_cluster/health?timeout=50s&pretty"
{
  "cluster_name" : "elasticsearch",
  "status" : "green",
  "timed_out" : false,
  "number_of_nodes" : 3,
  "number_of_data_nodes" : 3,
  "active_primary_shards" : 24,
  "active_shards" : 72,
  "relocating_shards" : 0,
  "initializing_shards" : 0,
  "unassigned_shards" : 0,
  "delayed_unassigned_shards" : 0,
  "number_of_pending_tasks" : 0,
  "number_of_in_flight_fetch" : 0,
  "task_max_waiting_in_queue_millis" : 0,
  "active_shards_percent_as_number" : 100.0
}
```

## CLI

### Mcrypt deprecation warnings

```
PHP Deprecated: Return type of phpseclib_mcrypt_filter::filter($in, $out, &$consumed, $closing) should either be compatible with php_user_filter::filter($in, $out, &$consumed, bool $closing): int, or the #[\ReturnTypeWillChange] attribute should be used to temporarily suppress the notice in vendor/phpseclib/mcrypt_compat/lib/mcrypt.php on line 1107

PHP Deprecated: Return type of phpseclib_mcrypt_filter::onCreate() should either be compatible with php_user_filter::onCreate(): bool, or the #[\ReturnTypeWillChange] attribute should be used to temporarily suppress the notice in vendor/phpseclib/mcrypt_compat/lib/mcrypt.php on line 1158
```

Warnings like these indicate a mismatch between the PHP version being used and the dependencies installed. `mcrypt` is deprecated in favour of Sodium now, so this indicates the PHP version is too old for the dependencies installed.

### `Could not open input file: bin/magento`, after running Composer commands

Something (e.g. A post-update script or hook) threw an error and prevented composer from copying the core Magento framework files from vendor to their appropriate places in the Magento root folder.

The solution is to tell composer to reinstall it:

```shell
composer reinstall magento/product-community-edition
```

If that doesn't work, try backing up the vendor folder and running composer install again:

``shell
mv vendor/ vendor_bak/
composer install
``

### `bin/magento` command returns the command prompt without producing any output / 'Magento Core Commands cannot be loaded. Please verify if "bin/magento" is running.'

Code completion erroneously added the statement `use Magento\Tests\NamingConvention\true\string;` to the top of a class.

Removing that line solved the problem.

### Column not found: 1054 Unknown column 'at_special_to_date_default.value' in 'where clause'

```shell
SQLSTATE[42S22]: Column not found: 1054 Unknown column 'at_special_to_date_default.value' in 'where clause', query was: SELECT `e`.`entity_id` FROM `catalog_product_entity` AS `e`
 INNER JOIN `catalog_category_product_index_store1` AS `cat_index` ON cat_index.product_id=e.entity_id AND cat_index.store_id=1 AND cat_index.visibility IN(2, 4) AND cat_index.category_id=2
 INNER JOIN `catalog_product_index_price` AS `price_index` ON price_index.entity_id = e.entity_id AND price_index.customer_group_id = '0' AND price_index.website_id = '1'
```

### Interface "Amasty\Rules\Api\ExtendedValidatorInterface" not found

### "Cannot instantiate interface" (general debugging guidelines)

- Search the most likely areas in the codebase for the class which can't be instantiated
- If the class appears as a constructor argument, verify there is a matching `preference` entry in the `di.xml`
- Verify that the `di.xml` is defined in the appropriate scope

### Cannot instantiate interface Magento\AdobeImsApi\Api\ConfigInterface#0

Disable the following modules:

Magento_AdminAdobeIms
Magento_AdobeIms
Magento_AdobeImsApi
Magento_AdobeStockAdminUi

Clear the caches, generated code etc

### Incompatible argument type: Required type: \Amasty\ShopbyBase\Model\FilterSettingFactory. Actual type: \Magento\Framework\App\Helper\Context; File:
/var/www/html/vendorname/projects/mlnb/html/vendor/amasty/shopby/Helper/FilterSetting.php

```
$ bin/magento setup:di:compile
Compilation was started.
Interception cache generation... 6/9 [==================>---------]  66% 38 secs 672.0 MiBErrors during compilation:
	Amasty\Shopby\Helper\FilterSetting
		Incompatible argument type: Required type: \Amasty\ShopbyBase\Model\FilterSettingFactory. Actual type: \Magento\Framework\App\Helper\Context; File: 
/var/www/html/vendorname/projects/mlnb/html/vendor/amasty/shopby/Helper/FilterSetting.php

Total Errors Count: 1

In Log.php line 92:
                            
  Error during compilation  
                            

setup:di:compile [-h|--help] [-q|--quiet] [-v|vv|vvv|--verbose] [-V|--version] [--ansi] [--no-ansi] [-n|--no-interaction] [--root-dir [ROOT-DIR]] [--skip-config] [--skip-root-check] [--skip-core-commands [SKIP-CORE-COMMANDS]] [--skip-magento-compatibility-check] [--] <command>
```

This is most likely caused by an invalid install of the Amasty Improved Layered Navigation extension.

The extension should be installed/upgraded by running the following commands:

```shell
composer require amasty/shopby:2.19.3
composer require amasty/module-shop-by-base:2.16.3
```


### 'Interface 'Vertex\Tax\Model\Flexfield\Processor\InvoiceFlexFieldProcessorInterface' not found' when running `setup:di:compile'` command

```bash
Compilation was started.
Repositories code generation... 1/7 [====>-----------------------]  14% < 1 sec 96.0 MiBPHP Fatal error:  Interface 'Vertex\Tax\Model\Flexfield\Processor\InvoiceFlexFieldProcessorInterface' not found in /var/www/html/vendorname/projects/moore-large-co/html/vendor/vertex/module-tax/Model/FlexField/Processor/OrderCurrencyGetterProcessor.php on line 24

Fatal error: Interface 'Vertex\Tax\Model\Flexfield\Processor\InvoiceFlexFieldProcessorInterface' not found in /var/www/html/vendorname/projects/moore-large-co/html/vendor/vertex/module-tax/Model/FlexField/Processor/OrderCurrencyGetterProcessor.php on line 24
```

This is because the namespace contains a typo. In `VertexTax/Model/FlexField/Processor/OrderCurrencyGetterProcessor.php`, the namespace should be `namespace Vertex\Tax\Model\FlexField\Processor;`. Note that `FlexField` is spelt with two upper-case F's, rather than `Flexfield`.

### 'There are no commands defined in the ... namespace'

* Run this command to get a more intuitive error message: `php bin/magento list`
* Clear all generated files: `var/di`, `var/cache`, `var/generated`, `generation`.
* Run the command with the flag `-vvv` to print out a backtrace
* This could be a result of an invalid module `composer.json` file. Progressively disable modules until the message disappears, or there are no modules to disable.
* Also happens when the module name in module.xml does not match with path based namespace. Please check your module name again: app/code/Vendor/myModuleName/etc/module.xml. More info: https://gist.github.com/bka/d44fb33d1eaf780e1b76
* Check file and folder permissions and ownership on `var` and `pub` directories.
* Validate the XML of all custom modules - there may be a syntax error or (more likely) a problem with the XML not validating against the XSD
* If you have used a code-generation tool, then it may have generated a file with no meaningful content, e.g. A `di.xml` file with no dependencies defined. Verify that all the files in all custom modules have valid content. 

### 'Class `ProcessEight\ModuleManager\Command\Module\Add\BinMagentoCommandCommand\Interceptor` does not exist'

This may happen if you manually install a new module which has dependencies (perhaps from a 3rd-party module) which has not been installed.

For example, `ProcessEight_ModuleManager` depends on the package `league/pipeline`. If `league/pipeline` is not already installed, then this error will be triggered. 

Running `setup:di:compile` gives us the vital clue to solve this problem:

```bash
zone8@zone8-aurora-r5:/var/www/html/jacobs-turner/trespass-m2/html$ mr2 set:up
PHP 7.2.22-1+ubuntu16.04.1+deb.sury.org+1 (cli) (built: Sep  2 2019 12:54:12) ( NTS )
Copyright (c) 1997-2018 The PHP Group
Zend Engine v3.2.0, Copyright (c) 1998-2018 Zend Technologies
Cache cleared successfully
File system cleanup:
/var/www/html/jacobs-turner/trespass-m2/html/generated/code/Composer
/var/www/html/jacobs-turner/trespass-m2/html/generated/code/MSP
/var/www/html/jacobs-turner/trespass-m2/html/generated/code/Magento
/var/www/html/jacobs-turner/trespass-m2/html/generated/code/ProcessEight
/var/www/html/jacobs-turner/trespass-m2/html/generated/code/Symfony
The directory '/var/www/html/jacobs-turner/trespass-m2/html/generated/metadata/' doesn't exist - skipping cleanup
Updating modules:
Class ProcessEight\ModuleManager\Command\Module\Add\BinMagentoCommandCommand\Interceptor does not exist
zone8@zone8-aurora-r5:/var/www/html/jacobs-turner/trespass-m2/html$ mr2 setup:di:compile
PHP 7.2.22-1+ubuntu16.04.1+deb.sury.org+1 (cli) (built: Sep  2 2019 12:54:12) ( NTS )
Copyright (c) 1997-2018 The PHP Group
Zend Engine v3.2.0, Copyright (c) 1998-2018 Zend Technologies
Compilation was started.
Interceptors generation... 4/7 [================>-----------]  57% 9 secs 273.0 MiB

  [RuntimeException]                                                                                 
  
  Class League\Pipeline\Pipeline does not exist
  
  Class ProcessEight\ModuleManager\Command\BaseCommand\Interceptor generation error: The requested class did not generate properly, because the 'generated' directory permission is read-only. If --- aft  
  er running the 'bin/magento setup:di:compile' CLI command when the 'generated' directory permission is set to write --- the requested class did not generate properly, then you must add the generated   
  class object to the signature of the related construct method, only.

setup:di:compile [-h|--help] [-q|--quiet] [-v|vv|vvv|--verbose] [-V|--version] [--ansi] [--no-ansi] [-n|--no-interaction] [--root-dir [ROOT-DIR]] [--skip-config] [--skip-root-check] [--skip-core-commands [SKIP-CORE-COMMANDS]] [--] <command>

zone8@zone8-aurora-r5:/var/www/html/jacobs-turner/trespass-m2/html$
```

The answer, then, is to simply `composer require` the `league/pipeline` package.

## API

### GraphQL: Unexpected non-whitespace character after JSON at position 2

Making a GraphQL request results in the following response:
```json
{
  "errors": [
    {
      "message": "Unexpected non-whitespace character after JSON at position 2",
      "stack": "SyntaxError: Unexpected non-whitespace character after JSON at position 2"
    }
  ]
}
```
Try loading the `/graphql` URI in a browser to see if there are any errors. If there are, they will be more descriptive than the above, e.g:

```
1 exception(s):
Exception #0 (GraphQL\Error\SyntaxError): Syntax Error: Unexpected Name "Blog"

Exception #0 (GraphQL\Error\SyntaxError): Syntax Error: Unexpected Name "Blog"
<pre>#1 GraphQL\Language\Parser->parseDefinition() called at [vendor/webonyx/graphql-php/src/Language/Parser.php:484]
#2 GraphQL\Language\Parser->GraphQL\Language\{closure}() called at [vendor/webonyx/graphql-php/src/Language/Parser.php:450]
#3 GraphQL\Language\Parser->many() called at [vendor/webonyx/graphql-php/src/Language/Parser.php:486]
#4 GraphQL\Language\Parser->parseDocument() called at [vendor/webonyx/graphql-php/src/Language/Parser.php:192]
#5 GraphQL\Language\Parser::parse() called at [vendor/webonyx/graphql-php/src/Utils/BuildSchema.php:70]
#6 GraphQL\Utils\BuildSchema::build() called at [vendor/magento/framework/GraphQlSchemaStitching/GraphQlReader.php:192]
#7 Magento\Framework\GraphQlSchemaStitching\GraphQlReader->readPartialTypes() called at [vendor/magento/framework/GraphQlSchemaStitching/GraphQlReader.php:115]
#8 Magento\Framework\GraphQlSchemaStitching\GraphQlReader->read() called at [vendor/magento/framework/GraphQlSchemaStitching/Common/Reader.php:41]
#9 Magento\Framework\GraphQlSchemaStitching\Common\Reader->read() called at [vendor/magento/framework/Config/Data.php:105]
#10 Magento\Framework\Config\Data->initData() called at [vendor/magento/framework/Config/Data.php:93]
#11 Magento\Framework\Config\Data->__construct() called at [vendor/magento/framework/ObjectManager/Factory/AbstractFactory.php:121]
#12 Magento\Framework\ObjectManager\Factory\AbstractFactory->createObject() called at [vendor/magento/framework/ObjectManager/Factory/Dynamic/Developer.php:66]
#13 Magento\Framework\ObjectManager\Factory\Dynamic\Developer->create() called at [vendor/magento/framework/ObjectManager/ObjectManager.php:70]
#14 Magento\Framework\ObjectManager\ObjectManager->get() called at [vendor/magento/framework/ObjectManager/Factory/AbstractFactory.php:170]
#15 Magento\Framework\ObjectManager\Factory\AbstractFactory->resolveArgument() called at [vendor/magento/framework/ObjectManager/Factory/AbstractFactory.php:276]
#16 Magento\Framework\ObjectManager\Factory\AbstractFactory->getResolvedArgument() called at [vendor/magento/framework/ObjectManager/Factory/AbstractFactory.php:239]
#17 Magento\Framework\ObjectManager\Factory\AbstractFactory->resolveArgumentsInRuntime() called at [vendor/magento/framework/ObjectManager/Factory/Dynamic/Developer.php:34]
#18 Magento\Framework\ObjectManager\Factory\Dynamic\Developer->_resolveArguments() called at [vendor/magento/framework/ObjectManager/Factory/Dynamic/Developer.php:59]
#19 Magento\Framework\ObjectManager\Factory\Dynamic\Developer->create() called at [vendor/magento/framework/ObjectManager/ObjectManager.php:70]
#20 Magento\Framework\ObjectManager\ObjectManager->get() called at [vendor/magento/framework/ObjectManager/Factory/AbstractFactory.php:170]
#21 Magento\Framework\ObjectManager\Factory\AbstractFactory->resolveArgument() called at [vendor/magento/framework/ObjectManager/Factory/AbstractFactory.php:276]
#22 Magento\Framework\ObjectManager\Factory\AbstractFactory->getResolvedArgument() called at [vendor/magento/framework/ObjectManager/Factory/AbstractFactory.php:239]
#23 Magento\Framework\ObjectManager\Factory\AbstractFactory->resolveArgumentsInRuntime() called at [vendor/magento/framework/ObjectManager/Factory/Dynamic/Developer.php:34]
#24 Magento\Framework\ObjectManager\Factory\Dynamic\Developer->_resolveArguments() called at [vendor/magento/framework/ObjectManager/Factory/Dynamic/Developer.php:59]
#25 Magento\Framework\ObjectManager\Factory\Dynamic\Developer->create() called at [vendor/magento/framework/ObjectManager/ObjectManager.php:70]
#26 Magento\Framework\ObjectManager\ObjectManager->get() called at [vendor/magento/framework/ObjectManager/Factory/AbstractFactory.php:170]
#27 Magento\Framework\ObjectManager\Factory\AbstractFactory->resolveArgument() called at [vendor/magento/framework/ObjectManager/Factory/AbstractFactory.php:276]
#28 Magento\Framework\ObjectManager\Factory\AbstractFactory->getResolvedArgument() called at [vendor/magento/framework/ObjectManager/Factory/AbstractFactory.php:239]
#29 Magento\Framework\ObjectManager\Factory\AbstractFactory->resolveArgumentsInRuntime() called at [vendor/magento/framework/ObjectManager/Factory/Dynamic/Developer.php:34]
#30 Magento\Framework\ObjectManager\Factory\Dynamic\Developer->_resolveArguments() called at [vendor/magento/framework/ObjectManager/Factory/Dynamic/Developer.php:59]
#31 Magento\Framework\ObjectManager\Factory\Dynamic\Developer->create() called at [vendor/magento/framework/ObjectManager/ObjectManager.php:70]
#32 Magento\Framework\ObjectManager\ObjectManager->get() called at [vendor/magento/framework/App/Http.php:115]
#33 Magento\Framework\App\Http->launch() called at [generated/code/Magento/Framework/App/Http/Interceptor.php:23]
#34 Magento\Framework\App\Http\Interceptor->launch() called at [vendor/magento/framework/App/Bootstrap.php:264]
#35 Magento\Framework\App\Bootstrap->run() called at [pub/index.php:30]
</pre>
```
This error happened because of using `#` to start a comment in an illegal place:

```graphql
# Comments are not allowed here
type Blog {
    # They are allowed here though
    title: String @doc(description: "The title of the blog")
}
```

### GraphQL: 'Cannot query field "..." on type "Query"'

This error occurs when the query is trying to access a field which does not exist in the schema. 

For example, if the schema is defined as:

```graphql
type Query {
    getBlog(id: ID!): Blog
}
```

Then the query should be:

```graphql
{
    getBlog(id: 1) {
        title
    }
}
```

If the query is:

```graphql
{
    getBlog(id: 1) {
        title
        author
    }
}
```

Then the error will be:

```json
{
  "errors": [
    {
      "message": "Cannot query field \"author\" on type \"Blog\".",
      "locations": [
        {
          "line": 4,
          "column": 9
        }
      ]
    }
  ]
}
```

### GraphQL: Field returns null in the result when it should return a value

This is most likely a problem with the resolver. Either it does not exist, or it is not returning the correct value.

Verify that it exists in the usual location (./ExampleVendor/ExampleModule/Model/Resolver/ExampleResolver.php), that the resolver class implements the `\Magento\Framework\GraphQl\Query\ResolverInterface` and it returns a value which matches the schema.

### "Consumer is not authorized to access %resources"

The first thing to try is to regenerate the authentication credentials (e.g. Bearer token) for the consumer. It's probably just expired or been revoked.

If that's not the problem, verify that the API user has the correct permissions to access the resource in the 'System, Permissions, All Users' area of the admin.

Here's the official docs: https://developer.adobe.com/commerce/webapi/rest/ and here's my in-depth exploration of Magento 2's API system: ['Anatomy of Magento 2: API'](https://gist.github.com/ProcessEight/74cd880994cff8fe2604e79da44b52f3)

## Frontend

### The contents from the "app/design/frontend/ProcessEight/ExampleTheme/etc/module.xml" file can't be read. Warning!file_get_contents(app/design/frontend/ProcessEight/ExampleTheme/etc/module.xml): Failed to open stream: No such file or directory

Themes don't have a `module.xml`. Verify that in the theme's `registration.php` file, `\Magento\Framework\Component\ComponentRegistrar::THEME` is used, instead of `\Magento\Framework\Component\ComponentRegistrar::MODULE`:

```php
<?php

declare(strict_types=1);

use Magento\Framework\Component\ComponentRegistrar;

ComponentRegistrar::register(
    ComponentRegistrar::THEME,
    'frontend/ProcessEight/ExampleTheme',
    __DIR__,
);
```

### Unable to load theme by specified key: 'Magento/luma'

Disabling the module `Smile_ElasticsuiteCms` fixed this. 

### Invalid template file: 'VendorName_KioskPaymentMethod::info/kioskpayment.phtml' in module: 'VendorName_KioskPaymentMethod' block's name: 'info\kioskpayment_0' [] []

Make sure the template file is defined in the correct area (i.e. The area where Magento is looking for it). 

Test your assumptions by debugging the template loading logic here: `\Magento\Framework\View\Element\Template::fetchView`

### The resource from “https://project.local/static/version1689851372/frontend/ThemeVendor/ThemeName/en_GB/modernizr/modernizr.js” was blocked due to MIME type (“text/html”) mismatch (X-Content-Type-Options: nosniff).

Check to see if the asset actually exists at that location. If not, the mime type mismatch may actually be caused by the browser mis-interpreting the 404 page as a valid JS asset. 

If the asset doesn't exist, then either add it or remove the reference which is trying to load it (check the `requirejs-config.js`).

### Clicking the pay now button disables it and nothing happens

- Disable reCAPTCHA
- Alternatively, verify you have reCAPTCHA configured correctly

### Error: Call to undefined method ReflectionUnionType::getName() in vendor/magento/framework/Interception/Code/Generator/Interceptor.php:216

This has been fixed in Magento 2.4.6

### No styles on frontend

Try running the static-content deployment command:

```shell
php bin/magento setup:static-content:deploy -f en_GB --area frontend
```

### Exception #0 (Magento\Framework\Exception\FileSystemException): The path "/var/www/html/m2/research/m24-example-modules/html/pub/static/." is not writable.

In developer mode, it is safe to chmod it to 775:

```shell
sudo chmod -Rf 775 /var/www/html/m2/research/m24-example-modules/html/pub/static/
```

### The files in my custom adminhtml theme are being ignored by Magento

Check that the theme is enabled. Adminhtml themes must be enabled by including `Magento_Theme` as a dependency in any modules' `module.xml`, or alternatively in `etc/adminhtml/di.xml` of any module. 

See https://devdocs.magento.com/guides/v2.4/frontend-dev-guide/themes/admin_theme_apply.html

### Cannot load fonts or XMLHttpRequest
The error will be something like:
```bash
(index):1 Access to font at 'http://trespass-m2.local/uk/static/frontend/Trespass/default/en_GB/fonts/trenda/trenda-semibold-webfont.woff2' from origin 'http://www.trespass-m2.local' has been blocked by CORS policy: No 'Access-Control-Allow-Origin' header is present on the requested resource.
```
The problem is that the font is on one domain (`http://trespass-m2.local/`) and is trying to be loaded from another domain (`http://www.trespass-m2.local` - note the www's).

Make sure that the domain requesting the font and the domain where the font is located are the same.

### Debugging frontend assets

Try loading the asset URL directly in the browser and looking for exceptions being printed or in your log is a good first step.

### Random 404 errors
If pages which used to work, e.g. Product pages suddenly return 404 errors, this could be indicative of an exception being thrown which prevents the rest of the page from rendering. Check the `exception.log` for errors.

### Seeing the server 404 page rather than the Magento one

- Verify that a 404 CMS page has been configured and enabled in the admin
  - Content > Elements > Pages > 404 Not Found
  - Ensure that page is configured as the CMS No Route Page' in Stores > Configuration > General > Web > Default pages
  - 

### Unable to retrieve deployment version of static files from the file system.
* Ensure that you are running in developer mode
* Ensure that there is a `.htaccess` file in `pub/static/`

### [Exception] Warning: Invalid argument supplied for foreach() in /vendor/magento/module-store/Model/Config/Processor/Fallback.php on line 125
Magento is trying to merge together all the config XML files of all modules, but has hit a variable which is empty where it is expecting a value. Therefore ensure Magento 2 has been installed correctly.

### Frontend asset URLs of the kind `http://www.example.co.uk/pub/static/version1510670604/frontend/Magento/luma/en_GB/mage/calendar.css` return a 404, even if `frontend/Magento/luma/en_GB/mage/calendar.css` does actually exist.
This is most likely a URL-rewriting issue.
* Verify that your vhost is setup correctly.
* Try using the default nginx config for M2 that comes with each install.

### Failed to load the "ProcessEight_CheckoutAddComponentToSidebarExample/js/view/FoolSample" component
* Clear any other JS errors which precede this one first
* Verify that the name of the component in the browser console is the same as the one which is included in the `define` list of dependencies in the uiComponent (verify they are the same case as well).
* In the browser console, check to see if the component is returning a 404. If so, the response may content a more useful error message
* Try disabling JS merging/bundling/minification (remember to re-enable them if necessary)
* Remove the `Magento_TestModule*` test modules, if they are present

### Unable to resolve the source file for 'frontend/Magento/luma/en_GB/ProcessEight_CheckoutAddComponentToSidebarExample/template/checkout/foolsample.html'
* Verify that the `checkout/foolsample.html` file is located in `{{Module_Root}}/view/frontend/web/template/` (i.e. The singular `template` folder, beneath `web`) and NOT in `{{Module_Root}}/view/frontend/templates`.

### My controller is not loading my layout updates

Verify the name of the Layout XML file is correct. For a router defined thus:
```xml
<config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
        xsi:noNamespaceSchemaLocation="urn:magento:framework:App/etc/routes.xsd">
    <!-- Router collects routes, parses request and performs matching of request to route. -->
    <router id="standard">
        <!-- Node: -->
        <!-- route: Defines a route used by a specific module -->
        <!-- Attributes: -->
        <!-- id: Unique route identifier, used to generate Layout XML handles and file names. Required. Value must match [A-Za-z0-9_]{3,}. Must be unique. -->
        <!-- frontName: URL part associated with route, forms first part of three-part URL structure of a Controller Action URL. Required. Value must match [A-Za-z0-9_\-]{1,}. Must be unique. -->
        <route id="planets_mercury"
               frontName="planets">
            <!-- name: Module is subscribed to process request with corresponding route front name. Required. Must be a valid Magento module name. -->
            <module name="Planets_Mercury"/>
        </route>
    </router>
</config>
```
...and with a file layout of:
```bash
-Planets
    -Mercury
        -Controller
            -Mercurycontrollerfoldername
                -View.php
```
This produces a URL of `http://m23-example-modules.local/planets/mercurycontrollerfoldername/view`

The Layout XML file should therefore be named (and located in) `html/app/code/Planets/Mercury/view/frontend/layout/planets_mercury_mercurycontrollerfoldername_view.xml`.

The name of the Layout XML file can be verified by looking at the `class` attribute of the `body` HTML tag in the source:
```html
<body ... class="planets_mercury-mercurycontrollerfoldername-view page-layout-3columns" ... >
```

**Note**: It is the `id` attribute of the `route` node in `routes.xml` (`planets_mercury` in this example), not the `frontName` attribute (`planets`), which determines the first part of the Layout XML Update filename.

### My template is not rendered at all

Enable template hints. The template may be being rendered, but no visible output produced.

Check the source code for HTML which appears in the template. Add a sentinel/flag message (e.g. `<h1>HERE I AM</h1>` or `<!-- abc123 -->` to the template to ensure there is something to find.

Double-check that your layout XML file is in the right location (e.g. Admin layout files must be created in the `view/adminhtml/layout` subdirectory).

Double-check that the name of the file matches the handle (i.e. Layout updates which affect the URL `http://magento2.localhost.com/admin/pulsestorm_hello_admin_backend/index/index/` should be stored in the file `view/layout/adminhtml/pulsestorm_hello_admin_backend.xml`).

Deliberately add a syntax error to the layout file you think is being used by Magento 2. If M2 reports no error, then either you're editing the wrong file, or the file has the wrong name.

Are other blocks in the same layout file being loaded? Add a new one or comment an existing one out to rule out caching issues.

If the block is being added to a container using the `reference` nodes, verify that the container/block being referenced actually exists in the final version of the layout XML tree for that page (it may been moved/removed by another module). Check the logs for messages like `Broken reference: the 'trade_user_create_captcha' element cannot be added as child to 'form.additional.info', because the latter doesn't exist [] []` or `Broken reference: the 'trade_user_create_captcha' tries to reorder itself towards '', but their parents are different: 'form.additional.info' and '' respectively. [] []`.

### `Exception #0 (Magento\Framework\Exception\LocalizedException): Object DOMDocument should be created.`

This error usually occurs when adding a new UI Component. The error usually means that:
* You've specified a `uiComponent` node, but Magento 2 can't find a matching configuration file. Verify that:
    * The file has been created in the `app/code/VendorNamespace/ModuleNamespace/view/adminhtml/ui_component/` folder.
    * The file is named after the `name` attribute of the `uiComponent` node (e.g. If you have `<uiComponent name="pulsestorm_simple_valid"/>` in your layout XML file, then the UI component configuration XML file should be named `pulsestorm_simple_valid.xml`)
    * The file is readable (has the correct permissions and ownership)

Less likely reasons:
* The UI Component XML is invalid
* A template referenced in a UI component is missing

Source: http://alanstorm.com/magento_simplest_ui_component/

### `Path "/var/www/html/m23-example-modules/htdocs/pub/static/" cannot be used with directory "/var/www/html/m23-example-modules/htdocs/pub/static/`
Make sure that the pub/static folder has the right permissions, ownership and gid bit set:
```bash
echo "# Set the group-id bit to ensure that files and directories are generated with the right ownership..."
sudo find var generated pub/static pub/media app/etc -type f -exec chmod g+w {} + &&
sudo find var generated pub/static pub/media app/etc -type d -exec chmod g+ws {} +
echo "# Ensure a clean slate by flushing selected directories..."
sudo rm -rf generated/code/ var/cache/ pub/static/* pub/media/*
```

### `Required parameter 'theme_dir' was not passed`

This is most likely caused by leftover data in the database after deleting a theme. 

Make sure that the theme is deleted from the `theme` table:
```bash
> select * from theme
+----------+-----------+---------------------------+----------------------------+----------------------------------+-------------+-----------+------+---------------------------+
| theme_id | parent_id | theme_path                | theme_title                | preview_image                    | is_featured | area      | type | code                      |
+----------+-----------+---------------------------+----------------------------+----------------------------------+-------------+-----------+------+---------------------------+
| 1        | <null>    | Magento/blank             | Magento Blank              | preview_image_5cb469fc54f48.jpeg | 0           | frontend  | 0    | Magento/blank             |
| 2        | <null>    | Magento/backend           | Magento 2 backend          | <null>                           | 0           | adminhtml | 0    | Magento/backend           |
| 3        | 1         | Magento/luma              | Magento Luma               | preview_image_5cb469fc5e23c.jpeg | 0           | frontend  | 0    | Magento/luma              |
| 4        | 1         | ProcessEight/ExampleTheme | ProcessEight Example Theme | preview_image_5d138dc84c646.jpeg | 0           | frontend  | 0    | ProcessEight/ExampleTheme |
+----------+-----------+---------------------------+----------------------------+----------------------------------+-------------+-----------+------+---------------------------+
> delete from theme where theme_id = 4
Query OK, 0 rows affected
Time: 0.002s
```

Make sure that the `design/theme/theme_id` path is deleted from the `core_config_data` table:

```bash
> select * from core_config_data where path like '%theme%'
+-----------+--------+----------+-----------------------+-------+
| config_id | scope  | scope_id | path                  | value |
+-----------+--------+----------+-----------------------+-------+
| 292       | stores | 1        | design/theme/theme_id | 7     |
+-----------+--------+----------+-----------------------+-------+
1 row in set
Time: 0.005s
> delete from core_config_data where config_id in (292)
1 row affected
Time: 0.005s
```

Delete any generated/copied files in the theme folders: 

```bash
rm -rf pub/static/frontend/<Theme_Vendor_Name>/ && rm -rf var/view_preprocessed/pub/static/frontend/<Theme_Vendor_Name>/
```
Don't bother deleting the theme folders for the adminhtml area (unless you're developing a custom admin theme).

Then clear cache, etc.

More information:

https://magento.stackexchange.com/a/128333

### `Refused to apply style from 'http://m23-example-modules.local/static/version1561564942/frontend/ProcessEight/ExampleTheme/en_GB/css/styles-m.css' because its MIME type ('text/plain') is not a supported stylesheet MIME type, and strict MIME checking is enabled`

There was most likely a error generating the CSS. Try to visit the URL (i.e. http://m23-example-modules.local/static/version1561564942/frontend/ProcessEight/ExampleTheme/en_GB/css/styles-m.css) directly - it will display the error message.

### JS objects are not of the expected type (e.g. They are instantiated as instances of `jquery-ui`)

The most likely scenario is that the object has been injected but assigned to the wrong object, e.g:

```js
define([
    'jquery',
    'Magento_Checkout/js/view/form/element/email',
    'ko',
    'Magento_Customer/js/model/customer',
    'Magento_Customer/js/action/check-email-availability',
    'Magento_Customer/js/action/login',
    'Magento_Checkout/js/model/quote',
    'Magento_Checkout/js/checkout-data',
    'Magento_Checkout/js/model/full-screen-loader',
    'Trespass_Checkout/js/model/step-validator',
    'mage/validation',
    'mage/storage',
    'Magento_Checkout/js/model/error-processor'
], function ($, Component, ko, customer, checkEmailAvailability, loginAction, quote, checkoutData, fullScreenLoader, stepValidator, storage, errorProcessor) {
    'use strict';
    
// JS file continues...
```

Note how there are 13 dependencies, but only 12 of them are injected into the `function` as parameters.

The parameter for `mage/validation` is missing, therefore `mage/validation` is erroneously assigned to the `storage` parameter. This produces the error where `storage` is initialised to the type `jquery-ui` rather than `mage/storage`.

Therefore, make sure that the list of dependencies matches the function parameter list.

### Assets are served over `HTTPS`, despite  the `web/secure/base_url` being set to a `http://...` address

Verify that the config options `web/secure/use_in_frontend` and `web/secure/use_in_adminhtml` options are disabled.

### 'We can't save the address: Email has a wrong format'

This is most likely to be a problem with logging in after having added products to the cart, which prevents the email from being saved to the quote correctly.

The simplest solution is to delete the quote from the database. 

Here are two related issues:
- [https://github.com/magento/magento2/issues/16101](when I checkout, magento2 tip me Email has a wrong format~ please~)
- [https://github.com/magento/magento2/issues/14964](Magento_Sales module fails to upgrade (email has a wrong format) #14964)

### Category titles appear with a different case on the frontend than on the backend

- Check that there is no CSS changing the case
- There may be a mismatch between the data being presented for a certain store front on the frontend and that in the admin. To quickly establish if this is the case, check the EAV table:

```shell
mysql> select * from catalog_category_entity_varchar where entity_id = 422;
+----------+--------------+----------+-----------+---------------------------------------------+
| value_id | attribute_id | store_id | entity_id | value                                       |
+----------+--------------+----------+-----------+---------------------------------------------+
|     3563 |           45 |        0 |       422 | PU Blocks                                   |
|     3568 |           45 |        1 |       422 | Pu Blocks                                   |
```
As you can see, the admin value is correct ('PU Blocks') but there is also an incorrect value added for the store scope '1' ('Pu Blocks').
Switching to the store scope in the admin will allow the incorrect value to appear and be updated, or you could just update the table directly.

### Compilation from source: LESS file is empty: frontend/ProcessEight/my-project/en_GB/css/critical.less

The styles need to be compiled. Run `yarn build` from the `<MAGENTO_BASE_DIR>/dev/tools/` directory.

## Email

### Ordered products table does not appear in the Order Email Template

The reason for the table of products not displaying is that the variable name has changed. The following line must be changed from

`order=$order area="frontend"`

to

`order_id=$order_id area="frontend"`

to make this work. 

## Hyva

###  [InvalidArgumentException] Could not find a matching version of package hyva-themes/magento2-reset-theme. Check the package spelling, your version constraint and that the package is available in a stability which matches your minimum-stability (stable).

Make sure you've added the Hyva Private Packagist repository:
```
composer config repositories.private-packagist composer https://hyva-themes.repo.packagist.com/eddev-co
```
Then try running the command:
```
/usr/bin/php7.3 /usr/local/bin/composer require hyva-themes/magento2-reset-theme hyva-themes/magento2-email-module hyva-themes/magento2-graphql-tokens hyva-themes/magento2-luma-checkout hyva-themes/magento2-theme-module
```

## MySQL

### SQLSTATE[42000]: Syntax error or access violation: 1075 Incorrect table definition; there can be only one auto column and it must be defined as a key, query was: ALTER TABLE `cms_page` MODIFY COLUMN `page_id` smallint  NOT NULL  AUTO_INCREMENT COMMENT "Entity ID", DROP PRIMARY KEY, ADD CONSTRAINT  PRIMARY KEY (`page_id`)

This is caused by importing a pre-existing database which doesn't have MSI enabled and then running setup:upgrade.

### mysqldump: Couldn't execute 'SHOW FUNCTION STATUS WHERE Db = 'magento2'': Column count of mysql.proc is wrong. Expected 21, found 20. Created with MariaDB 50717, now running 100427. Please use mysql_upgrade to fix this error (1558)

Run the `mysql_upgrade` program (note you need to run it as the same user as mysql):

```shell
sudo -u mysql mysql_upgrade --user=root --host=127.0.0.1
```

### `Types char is not declared`

This happens because an extension has declared a table column using the `char` type, but Magento's DTO does not support it. This error will happen during `setup:upgrade`. 

To fix it, add `<item name="char" xsi:type="object">\Magento\Framework\Setup\Declaration\Schema\Dto\Factories\StringBinary</item>` to `app/etc/di.xml`:

```xml
<config xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="urn:magento:framework:ObjectManager/etc/config.xsd">
    <type name="Magento\Framework\Setup\Declaration\Schema\Dto\ElementFactory">
        <arguments>
            <argument name="typeFactories" xsi:type="array">
                <item name="char" xsi:type="object">\Magento\Framework\Setup\Declaration\Schema\Dto\Factories\StringBinary</item>

```
See https://github.com/magento/magento2/pull/22442

### Delete duplicate rows from a table
```mysql
SELECT count(st.price_id) FROM source_table st
LEFT OUTER JOIN (
   SELECT MAX(customer_id) as customer_id, product_id, product_group, customer_discount_group, quantity_break, priority, final_price
   FROM source_table st
   GROUP BY product_id, product_group, customer_discount_group, quantity_break, priority, final_price
) as KeepRows ON
   st.customer_id = KeepRows.customer_id
WHERE
   KeepRows.customer_id IS NULL
ORDER BY st.price_id DESC
```

### Output query into TSV file
```bash
$ mysql -u <username> -p -N -B -e <query> <database_name> > <filename.csv>
$ mysql -u m2_dfl -p -N -B -e "SELECT st.price_id FROM source_table st" m2_dfl > output.csv
$ cat output.csv
123
124
125
...
```
**--skip-column-names, -N**

Do not write column names in results.

**--batch, -B**

Print results using tab as the column separator, with each row on a new line. With this option, mysql does not use the history file.

Batch mode results in non-tabular output format and escaping of special characters. Escaping may be disabled by using raw mode; see the description for the --raw option.

### Import CSV file

Before importing anything, you may want to disable foreign key checks. 

Open a new terminal window and execute the following:

```bash
> SET GLOBAL FOREIGN_KEY_CHECKS=0;
``` 

Do your importing in a different terminal window, then when you've finished, re-enable the checks using:

```bash
> SET GLOBAL FOREIGN_KEY_CHECKS=1;
``` 

#### From the CLI

```bash
mysqlimport 
    --columns="<comma-separated list of column names>" 
    --ignore-lines=1
    <database_name>
    </path/to/csv_file.csv>
    --user=<mysql_username>
    --password=<mysql_password>
    --fields-terminated-by=','
    --fields-optionally-enclosed-by='"'

# For example:
mysqlimport --columns="`head -n 1 /var/lib/mysql-files/catalog_eav_attribute.csv`" --ignore-lines=1 trespass_m2 /var/lib/mysql-files/catalog_eav_attribute.csv -u root -p --fields-terminated-by=',' --fields-optionally-enclosed-by='"'

```

**--columns="column_1,column_2[,column_n]**"

A comma-separated list of columns to import the CSV data into. CSV columns should map onto the column names of the table you're importing into.

This snippet:
```bash
`head -n 1 /var/lib/mysql-files/catalog_eav_attribute.csv`
```
is a clever little bit of code which extracts the first line of the CSV file (which usually has the column names) and populates the option with them once it is executed, so you don't have to copy/paste them or manually type them out. 

**--ignore-lines=1**

Ignores the first line in the file.

**trespass_m2**

The name of the database you want to import into.

**/var/lib/mysql-files/catalog_eav_attribute.csv**

The name and location of the CSV file to import. Note that the name of the file must match the name of the table you want to import into.

If you have MySQL compiled with `--secure-file-priv` option enabled (which is likely), you'll need to copy the CSV file into a special folder (in this example, `/var/lib/mysql-files/`). You can determine the location of this location for your MySQL instance by executing this query:

```bash
>  SHOW VARIABLES LIKE "secure_file_priv";
+------------------+-----------------------+
| Variable_name    | Value                 |
+------------------+-----------------------+
| secure_file_priv | /var/lib/mysql-files/ |
+------------------+-----------------------+
1 row in set
```

#### From inside mysql

```bash
> LOAD DATA LOCAL INFILE 'catalog_eav_attribute_for_import.csv'
                                 -> INTO TABLE catalog_eav_attribute
                                 -> FIELDS TERMINATED BY ','
                                 -> ENCLOSED BY '"'
                                 -> LINES TERMINATED BY '\n'
                                 -> (attribute_id,frontend_input_renderer,is_global,is_visible,is_sea
                                 -> rchable,is_filterable,is_comparable,is_visible_on_front,is_html_a
                                 -> llowed_on_front,is_used_for_price_rules,is_filterable_in_search,u
                                 -> sed_in_product_listing,used_for_sort_by,apply_to,is_visible_in_ad
                                 -> vanced_search,position,is_wysiwyg_enabled,is_used_for_promo_rules
                                 -> ,is_required_in_admin_store,is_used_in_grid,is_visible_in_grid,is
                                 -> _filterable_in_grid,search_weight,is_pagebuilder_enabled,addition
                                 -> al_data,is_displayed_in_autocomplete,is_used_in_spellcheck,facet_
                                 -> min_coverage_rate,facet_max_size,facet_sort_order,display_pattern
                                 -> ,display_precision,sort_order_asc_missing,sort_order_desc_missing
                                 -> ,trespass_ln_tooltip,trespass_ln_query_param,trespass_cp_carousel
                                 -> )
```

#### Replicating 'upsert' behaviour

If the table you're importing into already has data and some of that data needs to be updated (rather than just INSERTing everything), then you can use the `--replace` flag, which will mimic the 'INSERT ON DUPLICATE KEY UPDATE' functionality by deleting a matching row and then inserting the data from the CSV.

### 1148: The used command is not allowed with this MySQL version

When attempting to run the following command:
```
> LOAD DATA LOCAL INFILE '/var/www/html/clients/projects/my-project/html/path/to/csv/file.csv' INTO TABLE customer
                        ->                 FIELDS TERMINATED BY '|'
                        ->                 LINES TERMINATED BY '
                        -> '
                        ->                 IGNORE 1 LINES;
(1148, 'The used command is not allowed with this MySQL version')
```
The MySQL version in this case was 5.7:
```
$ mysql --version
mysql  Ver 14.14 Distrib 5.7.31-34, for debian-linux-gnu (x86_64) using  6.3
```
In this case, the problem is because MySQL has been configured with the `--local_infile` flag which specifically affects the `LOAD DATA` query.

The LOCAL modifier affects the expected location of the file and error handling. LOCAL works only if both the server and client have been configured to permit it. For example, if mysqld was started with the `local_infile` system variable disabled, LOCAL does not work. See the following section of the MySQL manual: [Security Considerations for LOAD DATA LOCAL](https://dev.mysql.com/doc/refman/5.7/en/load-data-local-security.html).

To check:
```
> SHOW VARIABLES LIKE "%infile%";
+---------------+-------+
| Variable_name | Value |
+---------------+-------+
| local_infile  | ON    |
+---------------+-------+
1 row in set
Time: 0.022s

``` 
See the MySQL manual for more information on the [LOAD DATA](https://dev.mysql.com/doc/refman/5.7/en/load-data.html) query.

If the error still occurs, even with the `local_infile` set, you can try passing it as a flag when running the MySQL client:
```
$ $ mysql -u root -p --local-infile=1
  Enter password: 
  Welcome to the MySQL monitor.  Commands end with ; or \g.
  Your MySQL connection id is 2693
  Server version: 5.7.31-34 Percona Server (GPL), Release '34', Revision '2e68637'

  ...

  mysql> use example_db;
  Database changed
  mysql> LOAD DATA LOCAL INFILE '/var/www/html/clients/projects/my-project/html/path/to/csv/file.csv' INTO TABLE customer
      -> FIELDS TERMINATED BY '|'
      -> LINES TERMINATED BY '
      '> '
      -> IGNORE 1 LINES;
  Query OK, 2620 rows affected, 862 warnings (0.06 sec)
  Records: 2620  Deleted: 0  Skipped: 0  Warnings: 862
  mysql> 

```

### The LOAD DATA query executes without error, but doesn't import anything - even if I move my file to the `secure_file_priv` location (usually `/var/lib/mysql-files/`)

It may be a platform issue - for example, the line ending character is different on different platforms. Try different combinations of line ending (e.g. `\r`, `\r\n` or just `\n`) as arguments to the `LINES TERMINATED BY` statement.

If the `LOAD DATA` query is being generated in a PHP file, you can use the platform-independent constant `PHP_EOL` to make sure the right line ending sequence is always used, no matter on what platform it is run:

```php
$sql = "LOAD DATA LOCAL INFILE '".$filename."' INTO TABLE ".$table."
        FIELDS TERMINATED BY '|'
        LINES TERMINATED BY '" . PHP_EOL . "'
        IGNORE 1 LINES;";
```

### Enabling `local_infile` in Magento 2

If you've got an extension which tries to execute a `LOAD DATA LOCAL` query, you'll need to pass in the `local-inline` flag to the PDO connection, when it is created.

To do that, add `'driver_options' => [PDO::MYSQL_ATTR_LOCAL_INFILE => 1],` to the `env.php` config for the appropriate connection:
```php
<?php
return [
    'db' => [
        'connection' => [
            'default' => [
                'host' => 'localhost',
                'dbname' => 'example_db',
                'username' => 'example_db',
                'password' => 'example_db',
                'model' => 'mysql4',
                'engine' => 'innodb',
                'initStatements' => 'SET NAMES utf8;',
                'active' => '1',
                'driver_options' => [PDO::MYSQL_ATTR_LOCAL_INFILE => 1],
            ]
        ],
```

### ERROR 1227 (42000) at line 16149: Access denied; you need (at least one of) the SUPER privilege(s) for this operation
This can happen if the `root` user is referenced somewhere in the SQL, but you are running the SQL as a user without `root` privileges. 

The fix is simply to replace the `root` user with another one. You can even use the MySQL `CURRENT_USER()` function if you don't want to hardcode a username.
```mysql
# Change this...
CREATE ALGORITHM=UNDEFINED DEFINER=`root`@`localhost` SQL SECURITY INVOKER VIEW `inventory_stock_1` AS SELECT ...
# ...to this:
CREATE ALGORITHM=UNDEFINED DEFINER=CURRENT_USER SQL SECURITY INVOKER VIEW `inventory_stock_1` AS SELECT ...
```

### 'Access denied; you need (at least one of) the PROCESS privilege(s) for this operation' when trying to dump tablespaces

Try using the `--no-tablespaces` switch.

Source: https://dba.stackexchange.com/questions/271981/access-denied-you-need-at-least-one-of-the-process-privileges-for-this-ope

## Nginx

### Upstream sent too big header while reading response header from upstream

Try adjusting the `fastcgi_buffers` and/or `fastcgi_buffer_size` directives:

```
# PHP entry point for main application
location ~ ^/(index|get|static|errors/report|errors/404|errors/503|health_check)\.php$ {
    try_files $uri =404;
    fastcgi_pass   fastcgi_backend_php73;
    
# I just decided to comment them out here:
#    fastcgi_buffers 16 16k; 
#    fastcgi_buffer_size 32k;

    fastcgi_param  PHP_FLAG  "session.auto_start=off \n suhosin.session.cryptua=off";
    fastcgi_param  PHP_VALUE "memory_limit=756M \n max_execution_time=18000";
    fastcgi_read_timeout 600s;
    fastcgi_connect_timeout 600s;

    fastcgi_index  index.php;
    fastcgi_param  SCRIPT_FILENAME  $document_root$fastcgi_script_name;
    include        fastcgi_params;
}
```

Source: https://stackoverflow.com/questions/25762111/how-to-fix-upstream-sent-too-big-header-while-reading-response-header-from-upstr

## RabbitMQ

Assuming the RabbitMQ service is running, you can access the GUI at `http://127.0.0.1:15672/`. The credentials are stored in the `app/etc/env.php` file.

You need to install the management plugin to access the GUI:

```shell
$ rabbitmq-plugins enable rabbitmq_management
Enabling plugins on node rabbit@zone8-aurora-r5:
rabbitmq_management
The following plugins have been configured:
  rabbitmq_management
  rabbitmq_management_agent
  rabbitmq_web_dispatch
Applying plugin configuration to rabbit@zone8-aurora-r5...
```

You can check the status of the RabbitMQ server by running:

```shell
$ service rabbitmq-server status
● rabbitmq-server.service - RabbitMQ broker
   Loaded: loaded (/lib/systemd/system/rabbitmq-server.service; enabled; vendor preset: enabled)
   Active: active (running) since Fri 2021-03-26 08:36:48 GMT; 2h 0min ago
 Main PID: 1706 (beam.smp)
   Status: "Initialized"
    Tasks: 36
   Memory: 135.1M
      CPU: 47.860s
   CGroup: /system.slice/rabbitmq-server.service
           ├─1706 /usr/lib/erlang/erts-10.7.2.8/bin/beam.smp -W w -MBas ageffcbf -MHas ageffcbf -MBlm
           ├─1778 erl_child_setup 32768
           ├─2383 /usr/lib/erlang/erts-10.7.2.8/bin/epmd -daemon
           ├─2418 inet_gethost 4
           └─2419 inet_gethost 4

Mar 26 08:36:47 zone8-aurora-r5 rabbitmq-server[1706]:   ##########  Licensed under the MPL 2.0. Webs
Mar 26 08:36:47 zone8-aurora-r5 rabbitmq-server[1706]:   Doc guides: https://rabbitmq.com/documentati
Mar 26 08:36:47 zone8-aurora-r5 rabbitmq-server[1706]:   Support:    https://rabbitmq.com/contact.htm
Mar 26 08:36:47 zone8-aurora-r5 rabbitmq-server[1706]:   Tutorials:  https://rabbitmq.com/getstarted.
Mar 26 08:36:47 zone8-aurora-r5 rabbitmq-server[1706]:   Monitoring: https://rabbitmq.com/monitoring.
Mar 26 08:36:47 zone8-aurora-r5 rabbitmq-server[1706]:   Logs: /var/log/rabbitmq/rabbit@zone8-aurora-
Mar 26 08:36:47 zone8-aurora-r5 rabbitmq-server[1706]:         /var/log/rabbitmq/rabbit@zone8-aurora-
Mar 26 08:36:47 zone8-aurora-r5 rabbitmq-server[1706]:   Config file(s): (none)
Mar 26 08:36:48 zone8-aurora-r5 rabbitmq-server[1706]:   Starting broker... completed with 3 plugins.
Mar 26 08:36:48 zone8-aurora-r5 systemd[1]: Started RabbitMQ broker.
```

## JavaScript

### Mixin does not work

The component that a mixin observes must return a UI component, jQuery widget or other. This return value is passed as the first argument to the mixin component. Make sure that the component you are overriding with a mixin returns an object.

## Resource scripts

### Setup script never runs

This could be several things:

* Install scripts will only ever run once. You must delete the row from the `setup_module` table to force it to run again:
```mysql
mysql> select * from setup_module where module = 'Magento_ExternalLinks';
+-----------------------+----------------+--------------+
| module                | schema_version | data_version |
+-----------------------+----------------+--------------+
| Magento_ExternalLinks | 2.0.0          | 2.0.0        |
+-----------------------+----------------+--------------+
1 row in set (0.00 sec)

mysql> delete from setup_module where module = 'Magento_ExternalLinks';
Query OK, 1 row affected (0.00 sec)

mysql> select * from setup_module where module = 'Magento_ExternalLinks';
Empty set (0.00 sec)
```
* The folder structure must exactly match the name given in the `registration.php` file, e.g. If the module name is `VendorName_ModuleName`, then the module folder must be `VendorName/ModuleName/Setup/InstallSchema.php`. Capitalisation is important.

Source: http://magento.stackexchange.com/questions/132052/magento2-setup-script-not-loaded

* Verify that the namespace is correct - especially if you copied in the script from another module.

### call_user_func(): Argument #1 ($callback) must be a valid callback, class "SuperTouch\Catalog\Setup\Patch\Data\AddWebRotateAttribute" not found

Full error message:
```
call_user_func(): Argument #1 ($callback) must be a valid callback, class "ProcessEight\Catalog\Setup\Patch\Data\AddWebRotateAttribute" not found#0 /var/www/html/processeight/projects/magento2-project/html/vendor/magento/framework/Setup/Patch/PatchRegistry.php(141): call_user_func(Array)
#1 /var/www/html/processeight/projects/magento2-project/html/vendor/magento/framework/Setup/Patch/PatchRegistry.php(207): Magento\Framework\Setup\Patch\PatchRegistry->getDependencies('ProcessEight\\Catalog\\Setup\\Patch\\Data\\AddWebRotateAttribute')
#2 /var/www/html/processeight/projects/magento2-project/html/vendor/magento/framework/Setup/Patch/PatchApplier.php(138): Magento\Framework\Setup\Patch\PatchRegistry->getIterator()
#3 /var/www/html/processeight/projects/magento2-project/html/setup/src/Magento/Setup/Model/Installer.php(1095): Magento\Framework\Setup\Patch\PatchApplier->applyDataPatch('ProcessEight_Catalog')
#4 /var/www/html/processeight/projects/magento2-project/html/setup/src/Magento/Setup/Model/Installer.php(961): Magento\Setup\Model\Installer->handleDBSchemaData(Object(Magento\Setup\Module\DataSetup), 'data', Array)
#5 /var/www/html/processeight/projects/magento2-project/html/setup/src/Magento/Setup/Console/Command/UpgradeCommand.php(147): Magento\Setup\Model\Installer->installDataFixtures(Array, true)
#6 /var/www/html/processeight/projects/magento2-project/html/vendor/symfony/console/Command/Command.php(255): Magento\Setup\Console\Command\UpgradeCommand->execute(Object(Symfony\Component\Console\Input\ArgvInput), Object(Symfony\Component\Console\Output\ConsoleOutput))
#7 /var/www/html/processeight/projects/magento2-project/html/vendor/symfony/console/Application.php(1021): Symfony\Component\Console\Command\Command->run(Object(Symfony\Component\Console\Input\ArgvInput), Object(Symfony\Component\Console\Output\ConsoleOutput))
#8 /var/www/html/processeight/projects/magento2-project/html/vendor/symfony/console/Application.php(275): Symfony\Component\Console\Application->doRunCommand(Object(Magento\Setup\Console\Command\UpgradeCommand), Object(Symfony\Component\Console\Input\ArgvInput), Object(Symfony\Component\Console\Output\ConsoleOutput))
#9 /var/www/html/processeight/projects/magento2-project/html/vendor/magento/framework/Console/Cli.php(116): Symfony\Component\Console\Application->doRun(Object(Symfony\Component\Console\Input\ArgvInput), Object(Symfony\Component\Console\Output\ConsoleOutput))
#10 /var/www/html/processeight/projects/magento2-project/html/vendor/symfony/console/Application.php(149): Magento\Framework\Console\Cli->doRun(Object(Symfony\Component\Console\Input\ArgvInput), Object(Symfony\Component\Console\Output\ConsoleOutput))
#11 /var/www/html/processeight/projects/magento2-project/html/bin/magento(23): Symfony\Component\Console\Application->run()
#12 {main}
```

Make sure that the class name of the setup patch class matches the namespace and file name of the class.

## Permissions

### Verify that permissions are setup correctly

- Add the CLI user (simon) to the web server group (www-data):
```bash
sudo adduser www-data simon
```
- Add the web server user (www-data) to the CLI group (simon):
```bash
sudo adduser simon www-data
```
Verify:
```bash
groups www-data
groups simon
```
Set the gid bit, so all new files and folders will be created with the right permissions:
```bash
sudo find var generated pub/static pub/media app/etc -type f -exec chmod g+w {} + && sudo find var generated pub/static pub/media app/etc -type d -exec chmod g+ws {} +
```
Finally, clear out any files from previous attempts, to ensure a clean slate:
```bash
sudo rm -rf generated/code/ var/cache/ pub/static/* pub/media/*
```
## Performance

Setup a load test on staging and do one part at a time:
1. Only home page, category, product pages,
2. Add shopping carts
3. Add checkout
4. etc

Disable all cronjobs during test runs first, then enable them.

Then you can pin point which part of the system causes an issue.

_Source: https://magechat.slack.com/archives/C03A38WJC/p1560208663092100_

## Deployment

### Magento Cloud

#### error: pub/front-static.php: No such file or directory

Try adding the following to your `composer.json`:
```json
    "extra": {
        "magento-deploystrategy": "copy",
    },
```

## Magento Enterprise/Commerce Edition

### All products disappear from categories on the frontend, but still appear in the admin

Try disabling Shared Catalog if it is enabled. It is part of the B2B feature. See Admin, Stores, Configuration, General, B2B Features.

## Extensions

### Error: Unknown named parameter $store_id in vendor/algolia/algoliasearch-magento-2/Model/Job.php:76



### Ebizmarts SagePaySuite/Opayo

See http://wiki.ebizmarts.com/common-problems

## WordPress integrations

### WordPress API not available. Hello (http://example.local/wp/index.php?rest_route=/fishpig/v1/hello) failed.



## Tools

### Deployer

#### There are no commands defined in the "maintenance" namespace.

```shell
[localhost] In Application.php line 606:
[localhost]   [Symfony\Component\Console\Exception\NamespaceNotFoundException]  
[localhost]   There are no commands defined in the "maintenance" namespace.     
[localhost]                       
```

Just comment out the relevant steps from the `deployer.php` script and run it again.

### Composer

#### Prompted for OAuth credentials when running `composer install`

If you're using Composer 1, try using Composer 2.2.21 or above

#### [Composer\Downloader\TransportException] curl error 28 while downloading https://composer.amasty.com/community/packages/amasty/base-1.14.1.zip: Connection timed out after 10003 milliseconds

- Verify that the composer credentials are correct 
- Verify they are defined in the correct place (`auth.json` or environment variables for AWS CodeBuild deployments)
- Verify the client is allowed to download this module (i.e. That they've paid for it and the license doesn't need renewing)
- Check with the vendor to see if there are any issues at their end

#### laminas/laminas-dependency-plugin is locked to version 2.5.0

- Downgrade the plugin. Using 2.2.0 with Magento Community 2.4.5-p1 has worked fine in the past.

#### Composer doesn't apply patches

Verify that either `patch` or `git` is installed on the target server.

### PhpStorm

#### PHP CS Fixer: PHP needs to be a minimum version of PHP 5.3.6 and maximum version of PHP 7.3.* (even if configured PHP language level is 7.3 or lower)

PhpStorm is trying to execute a tool (e.g. PHP CS Fixer), but it is using the default `php` command. On Ubuntu, this command is aliased (sym-linked) to the latest version of PHP, so if you have a higher version of PHP installed (e.g. 7.4), then PhpStorm will be (unknowingly) be using the wrong version. 

The solution, though not ideal, is to change the sym-link so it points to the desired version of PHP (7.3 in this case):

```php
$ cd /etc/alternatives/
zone8@zone8-aurora-r5:/etc/alternatives$ ls -laht php*
lrwxrwxrwx 1 root root 15 Nov  5 09:58 php -> /usr/bin/php7.4
lrwxrwxrwx 1 root root 24 Jan  3 09:06 php-fpm.sock -> /run/php/php7.4-fpm.sock
# ...
zone8@zone8-aurora-r5:/etc/alternatives$ sudo rm -f /etc/alternatives/php
[sudo] password for zone8: 
zone8@zone8-aurora-r5:/etc/alternatives$ sudo ln -s /usr/bin/php7.3 php
zone8@zone8-aurora-r5:/etc/alternatives$ ls -laht php*
lrwxrwxrwx 1 root root 15 Jan  3 09:56 php -> /usr/bin/php7.3
lrwxrwxrwx 1 root root 24 Jan  3 09:06 php-fpm.sock -> /run/php/php7.4-fpm.sock
# ...
```

Be aware, of course, that any programs/tools that _rely_ on this alias to run the latest version of PHP will probably break.

#### PhpStorm is stuck on `Updating indexes`

If you installed using JetBrains Toolbox, use `htop` tree view to find the `./jetbrains-toolbox-minimize` process and kill that.

### Magicento

#### Magicento 2 plugin for PhpStorm gives an error about the 'PHP response not being correct' or similar

Magicento 2 most likely cannot execute the PHP files it generates to do certain things. It can probably still create the files though (because that doesn't require executing PHP).

To solve, make sure the `/.idea/magicento2.xml` file looks like this:
```xml
/var/www/html/m2/research/m23-example-modules/html$ cat ../.idea/magicento2.xml 
<?xml version="1.0" encoding="UTF-8"?>
<project version="4">
  <component name="Magicento2Settings">
    <option name="enabled" value="true" />
    <option name="pathToMagento2Source" value="$PROJECT_DIR$/html/" />
    <option name="pathToPhp" value="" />
    <option name="urlToMagento" value="http://m23-example-modules.local/" />
    <option name="urlToEvalFolder" value="http://m23-example-modules.local/magicento2/" />
    <option name="useCustomEvalUrl" value="true" />
    <option name="useIdeaFolder" value="false" />
    <option name="useEvalCustomFolder" value="true" />
    <option name="evalCustomFolder" value="$PROJECT_DIR$/html/magicento2" />
    <option name="pathToBinMagento" value="$PROJECT_DIR$/html/" />
    <option name="phpBootstrapCode" value="chdir('/var/www/html/m2/research/m23-example-modules/html/magicento2/');&#10;require __DIR__ . '/../app/bootstrap.php';&#10;$bootstrap = Magento\Framework\App\Bootstrap::create(BP, $_SERVER);" />
    <option name="editableModules" value="Magento_AdobeIms" />
    <option name="cacheClassNames" value="true" />
    <option name="excludeTestFolders" value="true" />
    <option name="searchFilesInExternalLibrariesToo" value="true" />
  </component>
</project>
```
Additionally, setup a folder where Magicento 2 can create its files and is able to access and execute them. Then add a location block for the new folder in the `nginx.conf.local` (or whatever your Nginx config file is called) for the site:

```bash
location ~ ^/magicento2/(index|eval|eval_null|eval_commandline)\.php$ {
    root $MAGE_ROOT;

    fastcgi_pass   fastcgi_backend_php73;
    fastcgi_buffers 1024 4k;

    fastcgi_param  PHP_FLAG  "session.auto_start=off \n suhosin.session.cryptua=off";
    fastcgi_param  PHP_VALUE "memory_limit=8192M \n max_execution_time=18000";
    fastcgi_read_timeout 600s;
    fastcgi_connect_timeout 600s;

    fastcgi_index  index.php;
    fastcgi_param  SCRIPT_FILENAME  $document_root$fastcgi_script_name;
    include        fastcgi_params;
}
```

This is the first `location` block in the `nginx.conf.local` file. Restart nginx before testing any changes.

##### Magicento 2 still doesn't work

Check the PhpStorm Event Log. Any error messages emitted by PHP when called by Magicento 2 should appear there.

##### Deprecation messages appearing in the PhpStorm Event Log

```
10:36	Magicento2 Notification: PHP TEST ERROR: 
				Deprecated:  The each() function is deprecated. This message will be suppressed on further calls in /var/www/html/vendorname/projects/pavingdirect.com/html/vendor/colinmollenhour/cache-backend-file/File.php on line 81
				
				Warning:  "continue" targeting switch is equivalent to "break". Did you mean to use "continue 2"? in /var/www/html/vendorname/projects/pavingdirect.com/html/vendor/zendframework/zend-stdlib/src/ArrayObject.php on line 426
				MAGICENTO2 (show balloon)
```
Try changing the `fastcgi_pass` directive in the Magicento 2 nginx location to an earlier version of PHP.

### Xdebug

#### Installing/upgrading

General steps:

1. Download xdebug-X.Y.Z.tgz
1. Install the pre-requisites for compiling PHP extensions: `sudo apt-get install php-dev autoconf automake`
1. Unpack the downloaded file: `tar -xvzf xdebug-X.Y.Z.tgz`
1. Run: `cd xdebug-X.Y.Z`
1. Run the `phpize` command for your version of PHP: `phpize` .
 
    As part of its output it should show (for PHP7.3x):
    
    ```bash
    Configuring for:
    ...
    Zend Module Api No:      20180731
    Zend Extension Api No:   320180731
    ```
   
    If it does not, you are using the wrong `phpize`. Follow this [FAQ entry](https://xdebug.org/docs/faq#custom-phpize) before continuing.
    
1. Run the `configure` command for your version of PHP: `./configure [--with-php-config=/usr/bin/php-config7.3]`
1. Run: `make`
1. Run: `sudo cp modules/xdebug.so /usr/lib/php/{{ZEND_MODULE_API_NO}}` where `{{ZEND_MODULE_API_NO}}` matches the `Zend Module Api No` in the `phpize` output above (for PHP7.3x, the full path is `/usr/lib/php/20180731/`)
1. If you changed the name of the `xdebug.so` file to something else, edit `/etc/php/7.3/mods-available/xdebug.ini` and update the line to whatever you chose: `zend_extension = /usr/lib/php/{{ZEND_MODULE_API_NO}}/xdebug.so`
1. Restart PHP

For steps customised to your environment, use the wizard at https://xdebug.org/wizard.

After you've copied the `.so` module file to `/usr/lib/php/{{ZEND_MODULE_API_NO}}`, you can safely delete the extracted files in `xdebug-X.Y.Z/` (unless you want to compile it again). 

#### Error message: `Xdebug requires Zend Engine API version 320190902. The Zend Engine API version 320180731 which is installed, is outdated.`

Your Xdebug module does not match the PHP version it is configured for.

Make sure you use the compilation tools which correspond to your PHP version when compiling Xdebug from source.

For example, `Zend Engine API version 320180731` corresponds to PHP version 7.3x, so use `/usr/bin/phpize7.3` and `./configure --with-php-config=/usr/bin/php-config7.3` in the build steps above.

If you still get the error, then it's best to start from scratch. Don't bother to re-run the phpize or configure commands, because they have been 'tainted' by being compiled against the wrong PHP version.
 
- Remove the compiled `.so` module (i.e. `/usr/bin/php/{{ZEND_MODULE_API_NO}}/xdebug.so` if you used the default options). It's been compiled against the wrong version, so it'll never work. 
- In the folder where you extracted the files (`xdebug-X.Y.Z/` by default), run `phpize --clean` and the same command for the PHP version you're targeting (e.g. For PHP7.3x, run `phpize7.3 --clean`, which will remove any generated files from system locations:
 ```bash
 $ cd ~/Downloads/xdebug-2.9.8/
 $ phpize --clean
 Cleaning..
 $
```
- Remove the extracted files and any compiled files, so you are left with just the downloaded tar archive.
- Then try the '[General steps](#installingupgrading)' again from step 3.

#### Xdebug won't start

In order of likelihood:

- Verify that Xdebug is enabled
- Check `phpinfo()` and verify that Xdebug is loaded
- Verify that `export XDEBUG_CONFIG="idekey=PHPSTORM"` has been exported (for CLI scripts)
- Verify that the debugging cookie has been set (for HTTP requests)
- Verify that PhpStorm is listening to connections
- If using the built-in dev server, restart it after enabling Xdebug
- Restart PHP
- Clear website caches (e.g. Magento caches)
- Check that the version of Xdebug you've enabled matches the PHP version used to serve the website you're trying to debug
- Disable OPCache
- Disable Blackfire
- Ensure PhpStorm is not listening for connections in any other open windows
- If you've upgraded PHP recently, even if to a minor point release, use the custom installation instructions tool to download the matching version of Xdebug for your version of PHP and then re-compile Xdebug from scratch.

### Configuring Xdebug 3

Everything has changed in Xdebug 3.

Refer to https://xdebug.org/docs/step_debug to learn how to configure Xdebug for step-debugging in Xdebug 3.
