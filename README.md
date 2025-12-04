# Ivory Items Interactive Showcase

An interactive Jekyll-based website for showcasing ivory items.

## Setup

### Prerequisites
- Ruby (3.0 or higher)
- Bundler
- Jekyll

### Installation

1. Clone this repository
2. Install dependencies:
   ```bash
   bundle install
   ```

3. Run the site locally:
   ```bash
   bundle exec jekyll serve
   ```

4. Open your browser to `http://localhost:4000`

## Structure

- `_items/` - Collection of ivory items (each item is a markdown file)
- `_layouts/` - Page layouts
- `_includes/` - Reusable components
- `assets/` - CSS, JavaScript, and images
- `index.md` - Homepage

## Adding Items

To add a new ivory item:

1. Create a new markdown file in the `_items/` directory
2. Add front matter with the following fields:
   ```yaml
   ---
   layout: item
   title: "Item Title"
   image: /assets/images/your-image.jpg
   excerpt: "Brief description"
   metadata:
     Period: "Time period"
     Origin: "Place of origin"
     Dimensions: "Size"
     Material: "Ivory"
     Condition: "Current condition"
   ---
   ```
3. Add the detailed description in the markdown content

## Customization

- Edit `_config.yml` to change site settings
- Modify `assets/css/style.css` for styling
- Add interactive features in `assets/js/main.js`