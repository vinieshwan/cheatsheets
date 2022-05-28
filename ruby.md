# Ruby Cheatsheet

## Table of Contents

- <a href="#printing">Printing</a>
- <a href="#commenting">Commenting</a>
- <a href="#variables">Variables</a>
- <a href="#ranges">Ranges</a>
- Conditionals
- <a href="#strings">Strings</a>
- <a href="#numbers-and-booleans">Numbers and Booleans</a>
- <a href="#symbols">Symbols</a>
- Arrays
- Hashes
- <a href="#blocks-procs-lambdas">Blocks, Procs, Lambdas</a>
- Regular expressions
- Methods
- Classes
- Modules
- Mixins

## Printing

### Puts

```sh
    puts "Hello World!"
    puts "Welcome to Ruby Cheatsheet!"
```

```sh
    # OUTPUT
    Hello World!
    Welcome to Ruby Cheatsheet!
```

### Print

```sh
    print "Hello World!"
    print "Welcome to Ruby Cheatsheet!"
```

```sh
    # OUTPUT
    Hello World!Welcome to Ruby Cheatsheet!
```

### P

```sh
    p "Hello World!"
    p "Welcome to Ruby Cheatsheet!"
```

```sh
    # OUTPUT
    "Hello World!"
    "Welcome to Ruby Cheatsheet!"
```

## Commenting

### Single Line

```sh
    # "Hello World!"
```

### Multi Line

```sh
    =begin
    puts "Hello World!"
    puts "Welcome to Ruby Cheatsheet!"
    =end
```

## Variables

### Basic Variable Assignment

```sh
    word = "Hello World!"
```

### Parallel Variable Assignment

```sh
    a, b, c = 1, 2, 3
```

### Swapping Variable Values

```sh
    a, b = 1, 2

    a, b = b, a
```

### Constants

```sh
    SAMPLE = "Hello World!"
```

_`\*Please note that you will get a warning, if you overwrite a certain constant`_

## Ranges

### Numerical

```sh
    range = 1..5

    p range.first(5) # OUTPUT: [1, 2, 3, 4, 5]
    p range.last(5) # OUTPUT: [1, 2, 3, 4, 5]
    p range.size # OUTPUT: 5
    p range === 3 #OUTPUT : true
    p range === 6 #OUTPUT : false
    p range.include?(3) #OUTPUT : true
    p range.include?(6) #OUTPUT : false
    p rand(range) # Should generate any number from 1 to 5

    range = 1...5

    p range.first(5) # OUTPUT: [1, 2, 3, 4]
    p range.last(5) # OUTPUT: [1, 2, 3, 4]
    p range.size # OUTPUT: 4
    p range === 3 #OUTPUT : true
    p range === 5 #OUTPUT : false
    p range.include?(3) #OUTPUT : true
    p range.include?(5) #OUTPUT : false
    p rand(range) # Should generate any number from 1 to 4
```

### Alphabetical

```sh
    range = "a".."e"

    p range.first(5) # OUTPUT: ["a", "b", "c", "d", "e"]
    p range.last(5) # OUTPUT: ["a", "b", "c", "d", "e"]
    p range.size # OUTPUT: nil
    p range === "c" #OUTPUT : true
    p range === "f" #OUTPUT : false
    p range.include?("c") #OUTPUT : true
    p range.include?("f") #OUTPUT : false

    range = "a"..."e"

    p range.first(5) # OUTPUT: ["a", "b", "c", "d"]
    p range.last(5) # OUTPUT: ["a", "b", "c", "d"]
    p range.size # OUTPUT: nil
    p range === "c" #OUTPUT : true
    p range === "e" #OUTPUT : false
    p range.include?("c") #OUTPUT : true
    p range.include?("e") #OUTPUT : false
```

## Conditionals

## Strings

### Create Single Line String

```sh
    word = "Hello World!"
    p word # OUTPUT: "Hello World!"
    p word.class # OUTPUT: String


    word = String.new("Hello World!")
    p word # OUTPUT: "Hello World!"
    p word.class # OUTPUT: String
```

### Create Multi Line String

```sh
paragraph = <<S # You can use any character(s) you prefer after the << sign as your short identifier
    Ruby is an interpreted, high-level, general-purpose programming language which supports multiple programming paradigms.
In Ruby, everything is an object, including primitive data types.
S

puts paragraph
```

```sh
    # OUTPUT
    Ruby is an interpreted, high-level, general-purpose programming language which supports multiple programming paradigms.
In Ruby, everything is an object, including primitive data types.
```

### Escape Characters

```sh
    puts "Welcome to 'Ruby' Cheatsheet!" # OUTPUT: Welcome to 'Ruby' Cheatsheet!
    puts 'Welcome to "Ruby" Cheatsheet!' # OUTPUT: Welcome to "Ruby" Cheatsheet!

    puts "Welcome to "Ruby" Cheatsheet!" # This will error out
    puts 'Welcome to 'Ruby' Cheatsheet!' # This will error out

    puts "Welcome to \"Ruby\" Cheatsheet!" # OUTPUT: Welcome to "Ruby" Cheatsheet!
    puts 'Welcome to \'Ruby\' Cheatsheet!' # OUTPUT: Welcome to 'Ruby' Cheatsheet!

    puts "Welcome to\n'Ruby' Cheatsheet!"

    # OUTPUT:
    Welcome to
    'Ruby' Cheatsheet!

    puts "Welcome to\t'Ruby' Cheatsheet!" # OUTPUT: Welcome to      'Ruby' Cheatsheet!
```

### Single Quotes vs Double Quotes

```
    Single quotes will only explicitly render/print/hold the exact characters from the string.

    while...

    Double quotes will render/print/hold escape characters and interpolate strings
```

### Operators

```sh
    word = "Hello"

    p word == "Hello" # OUTPUT: true
    p word != "hello" # OUTPUT: true

    p "A" < "a" # OUTPUT: true
    p "Z" < "a" # OUTPUT: true
    p "z" > "A" # OUTPUT: true

    p "a" + "b" # OUTPUT: "ab"
```

### Concatenation

```sh
    word = "Hello"

    puts word + "World" # OUTPUT: HelloWorld
    puts word # OUTPUT: Hello

    puts word.concat("World") # OUTPUT: HelloWorld
    puts word # OUTPUT: HelloWorld

    word += "World"
    puts word # OUTPUT: HelloWorldWorld

    puts word << "World" #OUTPUT: HelloWorldWorldWorld
    puts word # OUTPUT: HelloWorldWorldWorld

    puts word.prepend("Hi, ") # OUTPUT: Hi, HelloWorldWorldWorld
    puts word # OUTPUT: Hi, HelloWorldWorldWorld
```

### Length, Size and Count

```sh
    word = "Hello"

    p word.length # OUTPUT: 5
    p " ".length # OUTPUT: 1
    p "".length # OUTPUT: 0

    p word.size # OUTPUT: 5
    p " ".size # OUTPUT: 1
    p "".size # OUTPUT: 0

    p word.count("l") # OUTPUT: 2
    p word.count("lo") # OUTPUT: 3
    p word.count("Hlo") # OUTPUT: 4
    p word.count("hlo") # OUTPUT: 3
```

### Character(s) Extraction

```sh
    word = "Hello"

    puts word[1] # OUTPUT: e
    puts word[-1] # OUTPUT: o
    p word[100] # OUTPUT: nil

    puts word.slice(1) # OUTPUT: e
    puts word.slice(-1) # OUTPUT: o
    p word.slice(100) # OUTPUT: nil

    puts word[1, 2] # OUTPUT: el
    puts word[-3, 2] # OUTPUT: ll
    p word[10, 2] # OUTPUT: nil

    puts word.slice(1, 2) # OUTPUT: el
    puts word.slice(-3, 2) # OUTPUT: ll
    p word.slice(10, 2) # OUTPUT: nil

    puts word[0..2] # OUTPUT: Hel
    puts word[-3..-1] # OUTPUT: llo
    p word[10..12] # OUTPUT: nil

    puts word.slice(0..2) # OUTPUT: Hel
    puts word.slice(-3..-1) # OUTPUT: llo
    p word.slice(10..12) # OUTPUT: nil

    puts word[0...2] # OUTPUT: He
    puts word[-3...-1] # OUTPUT: ll
    p word[10...12] # OUTPUT: nil

    puts word.slice(0...2) # OUTPUT: He
    puts word.slice(-3...-1) # OUTPUT: ll
    p word.slice(10...12) # OUTPUT: nil
```

### Overwrite Character(s) and Variables

```sh
    word = "Hello"

    word[1] = "a"
    puts word # OUTPUT: Hallo

    word[2, 2] = "l"
    puts word # OUTPUT: Halo

    word[1..2] = "ell"
    puts word # OUTPUT: Hello

    word[1...4] = "al"
    puts word # OUTPUT: Halo

    word = word.upcase
    puts word # OUTPUT: HALO

    word.downcase!
    puts word # OUTPUT: halo

    word.insert(1, "alo-h")
    puts word # OUTPUT: halo-halo

    word.insert(-1, "!")
    puts word # OUTPUT: halo-halo!
```

### Case Methods

```sh
    word = "Hello"

    puts word.capitalize # OUTPUT: Hello

    puts word.upcase # OUTPUT: HELLO

    puts word.downcase # OUTPUT: hello

    puts word.swapcase # OUTPUT: hELLO
```

### Reverse, Include, Between, Empty and Nil Methods

```sh
    word = "Hello"

    puts word.reverse # OUTPUT: olleH

    puts word.include?("H") # OUTPUT: true
    puts word.include?("h") # OUTPUT: false
    puts word.include?("lo") # OUTPUT: true
    puts word.include?("elo") # OUTPUT: false

    puts word.empty? # OUTPUT: false
    puts "".empty? # OUTPUT: true
    puts " ".empty? # OUTPUT: false
    puts word[100].empty? # OUTPUT: This will error out

    puts word.nil? # OUTPUT: false
    puts "".nil? # OUTPUT: false
    puts " ".nil? # OUTPUT: false
    puts word[100].nil? # OUTPUT: true
    puts "ball".between?("apple", "cat") # OUTPUT: true
    puts "caz".between?("apple", "cat") # OUTPUT: false
```

### Split, Join, Index, Squeeze, Clear and Delete Methods

```sh
    word = "Hello"

    p word.split("") # OUTPUT: ["H", "e", "l", "l", "o"]
    p "Hello World!".split(" ") # OUTPUT: ["Hello", "World!"]
    p word.split("ll") # OUTPUT: ["He", "o"]

    arr = word.split("")
    p arr # OUTPUT: ["H", "e", "l", "l", "o"]
    puts arr.join # OUTPUT: Hello
    puts arr.join("") # OUTPUT: Hello
    puts arr.join("--") # OUTPUT: H--e--l--l--o

    p word.index("l") # OUTPUT: 2
    p word.index("el") # OUTPUT: 1
    p word.index("z") # OUTPUT: nil
    p word.index("l", 3) # OUTPUT: 3

    p word.rindex("l") # OUTPUT: 3
    p word.rindex("el") # OUTPUT: 1
    p word.rindex("z") # OUTPUT: nil

    puts word.squeeze("l") # OUTPUT: Helo
    puts "Hello  World!! ".squeeze("! l") # OUTPUT: Helo World!

    word.clear
    p word # OUTPUT: ""

    word = "Hello"
    puts word.delete("hel") # OUTPUT: "Ho"
```

### Conversions

```sh
    p 123.to_s # OUTPUT: "123"
    p 123.24.to_s # OUTPUT: "123.24"

    p false.to_s # OUTPUT: "false"
    p true.to_s # OUTPUT: "true"

    p :age.to_s # OUTPUT: "age"
```

## Numbers and Booleans

### Types

```sh
    p 123.class # OUTPUT: Integer or Fixnum for older ruby versions
    p 9999999999999999999999999999999.class # OUTPUT: Integer or Bignum for older ruby versions

    p 123.45.class # OUTPUT: Float

    p true.class # OUTPUT: TrueClass
    p false.class # OUTPUT: FalseClass
```

### Conversions

```sh
    p "123".to_i # OUTPUT: 123
    p "123.24".to_i # OUTPUT: 123

    p "123".to_f # OUTPUT: 123.0
    p "123.24".to_f # OUTPUT: 123.24

    p 123.to_i # OUTPUT: 123
    p 123.24.to_i # OUTPUT: 123

    p 123.to_f # OUTPUT: 123.0
    p 123.24.to_f # OUTPUT: 123.24
```

### Operators

```sh
    p "123" == 123 # OUTPUT: false
    p 123 == 123 # OUTPUT: true
    p 123 == 123.0 # OUTPUT: true

    p "123" != 123 # OUTPUT: true
    p 123 != 123 # OUTPUT: false
    p 123 != 123.0 # OUTPUT: false

    p "123" > 124 # OUTPUT: this will error out
    p 123 > 124 # OUTPUT: false
    p 123 > 124.0 # OUTPUT: false

    p "123" >= 123 # OUTPUT: this will error out
    p 123 >= 123 # OUTPUT: true
    p 123 >= 123.0 # OUTPUT: true

    p "123" < 124 # OUTPUT: this will error out
    p 123 < 124 # OUTPUT: true
    p 123 < 124.0 # OUTPUT: true

    p "123" <= 123 # OUTPUT: this will error out
    p 123 <= 123 # OUTPUT: true
    p 123 <= 123.0 # OUTPUT: true

    p 10 + 1 # OUTPUT: 11
    p 15 - 3 # OUTPUT: 12
    p 5 * 5 # OUTPUT: 25
    p 10 / 2 # OUTPUT: 5
    p 10 % 3 # OUTPUT: 1
    p 2 ** 5 # OUTPUT: 32

    a = 5

    a += 2
    p a # OUTPUT: 7
    a -= 2
    p a # OUTPUT: 5
    a *= 2
    p a # OUTPUT: 10
    a /= 2
    p a # OUTPUT: 5
    a %= 2
    p a # OUTPUT: 1
    a **= 2
    p a # OUTPUT: 1
```

### Pred, Next, Odd, Even, Between, Floor, Ceil, Round, Abs Methods

```sh
    p 123.pred # OUTPUT: 122
    p 123.24.pred # OUTPUT: This will error out

    p 123.next # OUTPUT: 124
    p 123.24.next # OUTPUT: This will error out

    p 123.odd? # OUTPUT: true
    p 122.odd? # OUTPUT: false
    p 123.24.odd? # OUTPUT: This will error out

    p 123.even? # OUTPUT: false
    p 122.even? # OUTPUT: true
    p 123.24.even? # OUTPUT: This will error out

    p 3.between?(1, 5) # OUTPUT: true
    p 6.between?(1, 5) # OUTPUT: false
    p 5.6.between?(1.5, 5.6) # OUTPUT: true
    p 5.7.between?(1.5, 5.6) # OUTPUT: false

    p 3.floor # OUTPUT: 3
    p 3.6.floor # OUTPUT: 3

    p 3.ceil # OUTPUT: 3
    p 3.2.ceil # OUTPUT: 4

    p 3.round # OUTPUT: 3
    p 3.2.round # OUTPUT: 3
    p 3.26.round(1) # OUTPUT: 3.3
    p 3.235.round(2) # OUTPUT: 3.24

    p -3.abs # OUTPUT: 3
    p -3.6.abs # OUTPUT: 3.6
```

### Times, Step, Upto, Downto Block Methods

```sh
    3.times { |count| puts "Starts printing at count #{count}"}

    # OUTPUT
    # Starts printing at count 0
    # Starts printing at count 1
    # Starts printing at count 2

    4.times do |count|
        puts "Starts printing at count #{count}"
    end

    # OUTPUT
    # Starts printing at count 0
    # Starts printing at count 1
    # Starts printing at count 2
    # Starts printing at count 3

    1.step(10, 1) { |count| puts "Starts printing at count #{count}"}

    # OUTPUT
    # Starts printing at count 1
    # Starts printing at count 2
    # Starts printing at count 3
    # Starts printing at count 4
    # Starts printing at count 5
    # Starts printing at count 6
    # Starts printing at count 7
    # Starts printing at count 8
    # Starts printing at count 9
    # Starts printing at count 10

    0.step(10, 5) do |count|
        puts "Starts printing at count #{count}"
    end

    # OUTPUT
    # Starts printing at count 0
    # Starts printing at count 5
    # Starts printing at count 10

    1.upto(10) { |count| puts "Starts printing at count #{count}"}

    # OUTPUT
    # Starts printing at count 1
    # Starts printing at count 2
    # Starts printing at count 3
    # Starts printing at count 4
    # Starts printing at count 5
    # Starts printing at count 6
    # Starts printing at count 7
    # Starts printing at count 8
    # Starts printing at count 9
    # Starts printing at count 10

    1.upto(10) do |count|
        puts "Starts printing at count #{count}"
    end

    # OUTPUT
    # Starts printing at count 1
    # Starts printing at count 2
    # Starts printing at count 3
    # Starts printing at count 4
    # Starts printing at count 5
    # Starts printing at count 6
    # Starts printing at count 7
    # Starts printing at count 8
    # Starts printing at count 9
    # Starts printing at count 10

    5.downto(0) { |count| puts "Starts printing at count #{count}"}

    # OUTPUT
    # Starts printing at count 5
    # Starts printing at count 4
    # Starts printing at count 3
    # Starts printing at count 2
    # Starts printing at count 1
    # Starts printing at count 0

    5.downto(0) do |count|
        puts "Starts printing at count #{count}"
    end

    # OUTPUT
    # Starts printing at count 5
    # Starts printing at count 4
    # Starts printing at count 3
    # Starts printing at count 2
    # Starts printing at count 1
    # Starts printing at count 0
```

## Symbols

```sh
    # Symbols looks like this

    :age

    # It can be used as keys in hashes

    ball = {
        :color => "red",
        :shape => "circle",
        :size => "small"
    }

    # which is equivalent as well to

    ball = {
        color: "red",
        shape: "circle",
        size: "small"
    }

    # A string can be converted to symbol

    p "age".to_sym # OUTPUT: :age
    p "age".intern # OUTPUT: :age

    # Can be used as values in an array

    p list_of_symbols = %i[a b c] #OUTPUT: [:a, :b, :c]
    p ('a'..'d').map(&:to_sym) #OUTPUT: [:a, :b, :c, :d]
```

## Blocks, Procs, Lambdas

```sh
    def black_sample
        country = yield if block_given?

        puts "Welcome to #{country || "my world"}!"
    end

    black_sample { "Switzerland" }

    # OUTPUT: Welcome to Switzerland!

    black_sample

    # OUTPUT: Welcome to my world!

    def another_block(name)
        yield "Hi! My name is #{name}!" if block_given?
    end

    another_block('John') { |greetings| puts greetings }

    # OUTPUT: Hi! My name is John!

    square = Proc.new { |number| number ** 2 }

    p [2, 4, 6].map(&square)

    # OUTPUT: [4, 16, 36]

    # or

    p [2, 4, 6].map { |number| square.call(number) }
    # OUTPUT: [4, 16, 36]

    a = [2, 4, 6]
    b = [1, 2, 3, 4, 5]
    c = [3, 6, 9, 12]

    a_squared, b_squared, c_squared = [a, b, c].map { |list| list.map(&square) }

    p a_squared # OUTPUT: [4, 16, 36]
    p b_squared # OUTPUT: [1, 4, 9, 16, 25]
    p c_squared # OUTPUT: [9, 36, 81, 144]

    length_in_cm = [110, 120, 130, 140, 160]

    to_m = Proc.new { |length| (length / 100.to_f).round(2) }
    to_f = Proc.new { |length| (length / 30.48).round(2) }
    to_mm = Proc.new { |length| (length * 10.to_f).round(2) }
    to_km = Proc.new { |length| (length / 100000.to_f).round(4) }

    p length_in_cm.map(&to_m) # OUTPUT: [1.1, 1.2, 1.3, 1.4, 1.6]
    p length_in_cm.map(&to_f) # OUTPUT: [3.61, 3.94, 4.27, 4.59, 5.25]
    p length_in_cm.map(&to_mm) # OUTPUT: [1100.0, 1200.0, 1300.0, 1400.0, 1600.0]
    p length_in_cm.map(&to_km) # OUTPUT: [0.0011, 0.0012, 0.0013, 0.0014, 0.0016]

    ages = [20, 16, 12, 21, 32, 18]

    is_allowed = Proc.new do | age |
        age >= 18
    end

    p ages.select(&is_allowed) # OUTPUT: [20, 21, 32, 18]
    p ages.reject(&is_allowed) # OUTPUT: [16, 12]

    def greetings
        yield if block_given?
    end

    phrase = Proc.new do
        puts "Hello World!"
    end

    greetings(&phrase) # OUTPUT: Hello World!

    # or

    phrase.call # OUTPUT: Hello World!

    # method conversion to proc

    p ages.select(&:even?) # OUTPUT: [20, 16, 12, 32, 18]

   def pokemon_fight(player1, player2, &proc_func)
        puts "Welcome to pokemon fight #{player1} and #{player2}!"

        proc_func.call(player1, player2)
    end

    fight_welcome_message = Proc.new do |player1, player2|
        puts "In the right corner we have #{player1}!"
        puts "In the left corner we have #{player2}!"
        puts "Fight!"
    end

    pokemon_fight("Pikachu", "Snorlax", &fight_welcome_message)

    # OUTPUT:

    # Welcome to pokemon fight Pikachu and Snorlax!
    # In the right corner we have Pikachu!
    # In the left corner we have Snorlax!
    # Fight!
```
