# anonymoussc.github.io

This is the source code for the anonymoussc.github.io website, built using Jekyll static site generator and hosted on GitHub Pages.

## About

This is a personal blog/site named "anonymoussc" with various social media integrations and contact options. The site features posts with pagination, social icons, and customizable appearance settings.

## Prerequisites

Before you begin, ensure you have the following installed on your system:

- [Ruby](https://www.ruby-lang.org/en/downloads/) (version 2.5.0 or higher)
- [RubyGems](https://rubygems.org/pages/download)
- [GCC and Make](https://gcc.gnu.org/) (for building native gems on Linux/Mac, Windows users may need [Devkit](https://rubyinstaller.org/downloads/))

For Windows users, RubyInstaller is recommended as it includes Ruby, RubyGems, and Devkit.

## Installation

1. Clone the repository:
```bash
git clone https://github.com/anonymoussc/anonymoussc.github.io.git
cd anonymoussc.github.io
```

2. Install Bundler (if not already installed):
```bash
gem install bundler
```

3. Install the required gems:
```bash
bundle install
```

Note: On Windows, the `wdm` gem is included for proper file watching functionality. On Linux/Mac, you might need to install additional packages if you encounter issues with file watching.

## Running the Site Locally

1. Start the Jekyll server:
```bash
bundle exec jekyll serve
```

2. Open your browser and navigate to `http://localhost:4000`

The site will automatically rebuild when you make changes to the source files.

## Configuration

The site is configured through `_config.yml` which contains:
- Site name and description
- Author information
- Social media links
- Theme settings and colors
- Pagination settings
- Disqus integration for comments

## Project Structure

- `_config.yml` - Site configuration
- `_posts/` - Blog posts (in Markdown format)
- `_layouts/` - HTML templates
- `_includes/` - Reusable components
- `index.html` - Homepage
- `about.md` - About page
- `contact.html` - Contact page
- `Gemfile` - Ruby dependencies
- `assets/` - CSS, JavaScript, and other assets (if present)

## Deployment

This site is configured for GitHub Pages deployment. When pushed to a repository named `{username}.github.io`, it will automatically build and deploy.

For project pages (repositories not matching the username.github.io pattern), the site can be built to the `gh-pages` branch.

## Development Tips

- Use `bundle exec jekyll serve --livereload` for live reloading in modern browsers
- Draft posts can be stored in `_drafts/` and published with `jekyll serve --drafts`
- The `html-proofer` gem is included for link checking after builds

## Troubleshooting

If you encounter issues during setup:

1. Make sure all prerequisites are properly installed
2. On Windows, ensure Devkit is installed and integrated with Ruby
3. Run `bundle update` to ensure you have the latest compatible versions
4. Check that your Ruby version is compatible (2.5.0 or higher recommended)

## License

This project is licensed under the terms provided by GitHub Pages and Jekyll. See individual dependencies for their respective licenses.