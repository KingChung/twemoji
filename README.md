# Twemoji

Get emoji img by text.

## Installation

Add this line to your application's Gemfile:

```ruby
gem 'twemoji'
```

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install twemoji

## Usage

### API

#### `.find_by_text`

```ruby
> Twemoji.find_by_text(":heart_eyes:")
=> "1f60d"
```

#### `.find_by_code`

```ruby
> Twemoji.find_by_code("1f60d")
=> "1f60d"
```

#### `.find_by` text or code

```ruby
> Twemoji.find_by(text: ':heart_eyes:')
=> 1f60d

> Twemoji.find_by(code: '1f60d')
=> :heart_eyes:
```

#### `.parse`

```ruby
> Twemoji.parse 'I like chocolate :heart_eyes:!'
=> 'I like chololate <img class="emoji" draggable="false" alt=":heart_eyes:" src="https://twemoji.maxcdn.com/36x36/1f60d.png">'
```

##### asset_root

Default assets root url, by default will be `https://twemoji.maxcdn.com/`:

```ruby
> Twemoji.parse 'I like chocolate :heart_eyes:!', base: 'foocdn.com'
=> 'I like chololate <img class="emoji" draggable="false" alt=":heart_eyes:" src="https://foocdn.com/36x36/1f60d.png">'
```

##### file_ext

Default assets file extensions, by default '.svg'.

```ruby
> Twemoji.parse 'I like chocolate :heart_eyes:!', ext: '.png'
=> 'I like chololate <img class="emoji" draggable="false" alt=":heart_eyes:" src="https://twemoji.maxcdn.com/16x16/1f60d.png">'
```

##### image_size

Default assets/folder size, by default "36x36". Available via Twitter CDN: 16, 36, 72

Only applicable when file_ext is .png.

```ruby
> Twemoji.parse 'I like chocolate :heart_eyes:!', size: "72x72", ext: '.png'
=> 'I like chololate <img class="emoji" draggable="false" alt=":heart_eyes:" src="https://twemoji.maxcdn.com/72x72/1f60d.png">'
```

##### class_name

Default img css class name, by default "emoji".

```ruby
> Twemoji.parse 'I like chocolate :heart_eyes:!', class_name: 'superemoji'
=> 'I like chololate <img class="superemoji" draggable="false" alt=":heart_eyes:" src="https://twemoji.maxcdn.com/72x72/1f60d.png">'
```

## Contributing

1. Fork it ( https://github.com/[my-github-username]/twemoji/fork )
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create a new Pull Request