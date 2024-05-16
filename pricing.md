---
layout: page
title: Pricing
permalink: /pricing/
image: /assets/images/check_image_migrations.png
---
Add this line to your application's Gemfile:

```ruby
gem "decidim-decidim_awesome"
```
And then execute:

```bash
bundle
bundle exec rails decidim_decidim_awesome:install:migrations
bundle exec rails decidim:upgrade
bundle exec rails db:migrate
```
If you are upgrading from a version prior to 0.8, make sure to visit the URL `/admin/decidim_awesome/checks` and run image migrations for the old images:

![Check image migrations]({{ page.image }})


If you are a system admin, you can also perform this task by executing this rake task in the console:

```
RAILS_ENV=production bin/rails decidim_awesome:active_storage_migrations:migrate_from_carrierwave
```
Or check your migration status with:

```
RAILS_ENV=production bin/rails decidim_awesome:active_storage_migrations:check_migration_from_carrierwave
```

The correct version of Decidim Awesome should resolved automatically by the Bundler. However you can force some specific version using gem "decidim-decidim_awesome", "~> 0.10.0" in the Gemfile.

Depending on your Decidim version, choose the corresponding Awesome version to ensure compatibility:

| Awesome version |	Compatible Decidim versions |
| --------------- | --------------------------- |
| 0.10.0	      | >= 0.26.7, >= 0.27.3        |
| 0.9.2	          | >= 0.26.7, >= 0.27.3        |
| 0.9.x	          | 0.26.x, 0.27.x              |
| 0.8.x	          | 0.25.x, 0.26.x              |
| 0.7.x           |	0.23.x, 0.24.x              |
| 0.6.x           |	0.22.x, 0.23.x              |
| 0.5.x           |	0.21.x, 0.22.x              |

> *Heads up!*

> * version 0.10.0 requires database migrations! Don't forget the migrations step when updating.
> * version 0.8.0 removes CSS Themes for tenants. If you have been using them you will have to manually migrate them to custom styles.
> * version 0.8.0 uses ActiveStorage, same as Decidim 0.25. 2 new rake task have been introduced to facilitate the migration: `bin/rails decidim_awesome:active_storage_migrations:check_migration_from_carrierwave` and `bin/rails decidim_awesome:active_storage_migrations:migrate_from_carrierwave`
> * version 0.7.1 requires database migrations! Don't forget the migrations step when updating.
