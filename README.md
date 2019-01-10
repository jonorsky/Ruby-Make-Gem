# Ruby Make Local Gem
Make your own gem in Ruby

### Requirements

> Ruby


### Steps
#### 1. Create Project Structure of Gem Generator
```
mkdir own_gem
cd own_gem
mkdir lib
```

#### 2. Create Gem Spec using Template
```
Gem::Specification.new do |s|
  s.name = %q{local_gem}
  s.author = 'Jonorsky'
  s.version = "0.0.0"
  s.date = %q{2019-01-01}
  s.summary = %q{Gem Description}
  s.files = [
    "lib/Local_gem.rb"
  ]
  s.require_paths = ["lib"]
end
```

#### 3. - Add Code to lib
Put **1** ruby file in lib **/lib/local_gem.rb**
```
module Local_gem
  class Person
    def self.name?
      puts "Name: Jonorsky"
    end
  end
end
```

#### 4. - Generate or Build the Gem File

Build it using this command
```
gem build local_gem.gemspec
```

You should see the following output
```
Successfully built RubyGem
  Name: local_gem
  Version: 0.0.0
  File: local_gem-0.0.0.gem
```

> The Generated Gem will be rename as 'local_gem-0.0.0.gem'

> Gem name = concatenated s.name + '-' + s.version

> Now you create your own Gem and you can use it in other projects


## Install Your Created Gem
Make separate folder, for example in Desktop

```
cd Desktop
mkdir project
cd project
```

Create your Ruby File in project folder with **test_gem.rb**

```
require 'local_gem'

local_gem::Person.name?
```

Execute your ruby file
```
ruby test_gem.rb
```

**Output:**
```
Name: Jonorsky
```
