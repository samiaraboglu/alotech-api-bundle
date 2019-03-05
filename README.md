# alotech-api-bundle

Use the [AloTech PHP API](https://github.com/samiaraboglu/alotech-php-api).

### Download the Bundle

```console
$ composer require samiaraboglu/alotech-api-bundle
```

### Enable the Bundle

Registered bundles in the `app/AppKernel.php` file of your project:

```php
<?php
class AppKernel extends Kernel
{
    public function registerBundles()
    {
        $bundles = array(
            // ...
            new Samiax\AloTechApiBundle\SamiaxAloTechApiBundle(),
        );
        // ...
    }
    // ...
}
```

### Config
Add this to config.yml:

```yaml
samiax_alo_tech_api:
    username: "{USERNAME}"
    app_token: "{APP_TOKEN}"
```

### Example - Click 2 Call

```php
/**
 * @Route("/alotech/click2call/call", name="alotech/click2call/call")
 */
public function callAction(Request $request)
{
    $service = $this->get('samiax_alo_tech_api.alotech');

    $service->login('{EMAIL}');

    $service->click2Call->call('{PHONE_NUMBER}');

    return new Response();
}
```
