Vagrant Box for Ruby 1.9.3 Rails App Setup
------

- Install vagrant (test with 1.7.2) and virtualbox (tested with 4.3.16).
- Run `vagrant plugin install vagrant-vbguest` (tested with 0.10.0) and `vagrant plugin install vagrant-librarian-chef` (tested with 0.2.1)
- Run `vagrant up` from directory with `Vagrantfile`, _you may need to adjust forwarded port in Vagrantfile if there's a conflict_.
- Run `vagrant ssh`
- Change to /vagrant/todo dir: `cd /vagrant/todo`
- Run `bundle`
- Run `rbenv rehash`
- Run `psql -U postgres -h localhost`, ensure you have access via that command
- Run `rake db:create db:migrate db:seed`
- Run `rake db:test:prepare`
- Run `psql -U postgres -h localhost`, ensure `todo_development` and `todo_test` are created
- Run `bundle exec guard -p`
- Run `rails s`
- Hit on `localhost:3336`

- If you continue to see errors about guest addition mismatch between host and guest, go ahead and run `sudo ln -s /opt/VBoxGuestAdditions-4.3.10/lib/VBoxGuestAdditions /usr/lib/VBoxGuestAdditions`

You should now be setup.
