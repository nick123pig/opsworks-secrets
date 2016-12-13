# opsworks-secrets

## Configure
* Add to your cookbooks
* Put `secrets::configure` in your configure step

The file will look like this
```
$ cat /srv/www/yourapp/shared/config/secrets
ENV['VARNAME']=VALUE
ENV['VARNAME2']=VALUE
```

* You can then parse them in your app. For example, bootstrap in ruby
```ruby
path = '/srv/www/yourapp/shared/config/secrets'
File.open(path).each{|i| eval i} if File.exist?(path)
```
