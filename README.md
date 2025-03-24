# Kim Hamilton's Personal Website

This is my personal website built with Jekyll.

## Development Setup

### Prerequisites

- Ruby (managed via rbenv)
- Bundler
- Jekyll

### First-time Setup

1. Make sure rbenv is initialized (should be automatic if you have the following in your `.bash_profile`):
   ```bash
   eval "$(rbenv init -)"
   ```

2. Install the correct Ruby version:
   ```bash
   rbenv install 3.2.7  # if not already installed
   rbenv local 3.2.7    # sets project Ruby version
   ```

3. Install the correct Bundler version:
   ```bash
   gem install bundler:2.6.6
   ```

4. Install project dependencies:
   ```bash
   bundle install
   ```

### Running the Site

To start the development server:
```bash
bundle exec jekyll serve
```

The site will be available at [http://localhost:4000](http://localhost:4000)

### Project Structure

- `_posts/` - Blog posts in Markdown format
- `_layouts/` - HTML templates
- `_sass/` - Sass partials
- `assets/` - Static assets including CSS, images, etc.
  - `assets/css/style.scss` - Main Sass file that imports all partials (source file)
  - `assets/css/style.css` - Generated CSS file (do not edit directly - this is automatically generated from style.scss)

### Common Issues

1. If you see Ruby version or gem-related errors when running `jekyll serve`:
   - Make sure you're using `bundle exec jekyll serve`
   - Check that rbenv is initialized in your shell
   - Verify you're using Ruby 3.2.7 with `ruby -v`

2. If gems are missing:
   ```bash
   bundle install
   ```

3. If you need to reset your environment:
   ```bash
   rm -rf vendor/ Gemfile.lock
   bundle install
   ```
