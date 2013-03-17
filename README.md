# X-editable 1.4.3 for Rails 

[X-editable](https://github.com/vitalets/x-editable) is an in-place editing plugin with support for Twitter Bootstrap, jQuery UI or pure jQuery.

The `bootstrap-x-editable-rails` gem integrates `X-editable` with Rails asset pipeline. This gem only supports the Bootstrap part of X-editable.

## Usage

### Install bootstrap-x-editable-rails gem

Include `bootstrap-x-editable-rails` in Gemfile

    gem 'bootstrap-x-editable-rails'

Then run `bundle install`

### Include X-editable javascript

Add to your `app/assets/javascripts/application.js`

#### Popup version

    //= require bootstrap-editable

#### Inline version

    //= require bootstrap-editable-inline

### Include X-editable stylesheet

Add to your `app/assets/stylesheets/application.css`

    *= require bootstrap-editable

## Updating the gem
There are two rake tasks designed to ease the maintenance of this gem.

The `update` task pulls the latest X-editable code from github and places images, stylesheets and javascripts in the correct gem paths. It also changes background-image properties in the stylesheet to asset pipeline equivalents.

	rake update
	
The `build` task is a simple wrapper for `gem build`
	
	rake build
