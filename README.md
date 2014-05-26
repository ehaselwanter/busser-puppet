# Busser::Puppet

make test-kitchen happy. test-kitchen tries to install gems named after directories, unless they are excluded

sudo -E ${gem_bindir}/busser setup; sudo -E /tmp/busser/bin/busser plugin install busser-puppet busser-serverspec

```
module Kitchen

  class Busser

    def non_suite_dirs
      %w{data data_bags environments nodes roles}
    end
  end

end
```

so in order to be able to have a per suite `puppet` directory we create a fake gem until puppet is a first class citizen in test-kitchen.

