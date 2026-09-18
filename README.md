# Enable Swagger in Production for Magento 2 (SISL fork)

Re-enables the Swagger API documentation UI (`/swagger`) in Magento 2 **production mode**.
Magento disabled Swagger in production since 2.4.4, which is safe by default but a real
nuisance when you need to inspect or test the REST API on a staging or production-like
environment. This module adds a config flag to turn it back on where you want it.

Maintained fork of `integer-net/magento2-enable-swagger`, verified on **Magento 2.4.9 / PHP 8.4**.

## What changed vs upstream

- Bumped the `php` constraint from `~7.1 … ~8.1` to **8.1–8.5** — the original **would not
  install on PHP 8.3/8.4**, i.e. a hard block on Magento 2.4.9.
- Kept `magento/framework ^102.0.0||^103.0.0`; removed the post-install phpcs script.

> Enable it deliberately. Exposing Swagger in production has a security trade-off.

## Install

```bash
composer require sisl-source/magento2-enable-swagger
bin/magento module:enable IntegerNet_EnableSwagger
bin/magento setup:upgrade
```

Then enable it under *Stores → Configuration → Services → Swagger* and open `/swagger`.

## License

MIT (upstream, by integer_net). Maintained by [SISL](https://sisl.pl).

---

### Maintained by SISL

Maintained fork by **[SISL](https://sisl.pl)** — [Magento 2 development and modules](https://sisl.pl/moduly-magento). More self-hosted plugins: [SISL Marketplace](https://sisl.pl/sklep).