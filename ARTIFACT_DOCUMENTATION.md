# Food Customization and Informatica Master Data Management

## Artifact Name
**Food Customization and Informatica MDM - Multi-Platform Menu Data Delivery**

## Overview
Interactive HTML presentation demonstrating how Informatica Master Data Management (MDM) Hub solves the complex challenge of managing menu data across multiple delivery platforms (DoorDash, Grubhub, Uber Eats) for Quick Service Restaurants.

## Files
1. **food-customization-mdm.html** - Original version with technical comparisons
2. **food-customization-mdm-branded.html** - Branded version with Informatica colors, landing page, and sticky navigation

## Initial Prompts

### Prompt 1: Folder Creation
```
Create a new folder that stores any diagrams or html pages or markup
```

### Prompt 2: Main Artifact Creation
```
create a new artifact. Based on thie information, create a simple design with a header page about 
Food Customization and Informatica Master Data, leverage NotebookLLM master data notebook for context. 
Create a section for the 4 items in the menu information text, for each section compare the three 
outputs (DoorDash, Grubhub, Uber Eats) and create a simple graphic that shows the differences in how 
the data needs to be output. 

On the final summary slide, so an example of data sources like ERP, PLM, Excel, and other Quick Service 
Restraunt softwares, coming into Informatica MDM Hub, the hub converts the different source data models 
and standards into one cannonical model, MDM Hub standardized words such as Brands, sizes, Address etc. 
MDM Hub then builds on the data model to create an easy way to manage the food customization data via 
workflows and data stewardship. 

Lastly MDM Hub then leverages Informtaica Data and App Integrations to produce the three diffrent target 
models - Door Dash, Grubhub, Uber Eats. Make this artifact simple with clean graphics, make it so the 
text and formatting is editable. Allow for images to be added manually at a later date. Store in the 
artifacts folder.
```

### Prompt 3: Technical Details Addition
```
add this infor for the differences between the OLO platform While DoorDash, Grubhub, and Uber Eats all 
ingest the same core menu items and food customizations from an upstream PIM system like Informatica P360, 
their API architectures organize this data in fundamentally different ways.

1. Structural Design Models

DoorDash (Hierarchically Nested Tree): Data follows a strict parent-to-child lineage embedded directly 
inside a single object cascade. To find a modifier choice, the processing engine must drill deep into the 
specific menu, category, and item array where it resides.

Grubhub (Normalized Sibling Arrays): Data is entirely flattened at the root level into discrete, 
independent tables. Entities are linked exclusively via a web of string reference IDs ("items": ["ITEM_ID"]). 
No item or modifier data is ever nested inside another.

Uber Eats (Relational Entity Graph): Data treats menus, categories, items, and modifier groups as modular, 
globally unique entities mapped inside their own explicit root arrays. Cross-references are explicitly 
declared at each level to map relationships.

2. Pricing and Float Notation

DoorDash & Uber Eats: Use Integer Cents Only. A price of $12.99 must be multiplied by 100 to map as an 
exact integer value (1299). Decimal floats are rejected.

Grubhub: Uses standard Decimal Floats. Prices are sent natively as standard currency values (e.g., 10.00 
or 1.50).

3. Text and Localization Handling

DoorDash & Grubhub: Accept direct, flat text strings for consumer-facing names and descriptions 
(e.g., "name": "Classic Cheeseburger").

Uber Eats: Mandates a strict localization map structure. Every single text field must be isolated inside 
a nested translations block mapped to an ISO language code (e.g., {"title": {"translations": {"en_us": 
"Classic Cheeseburger"}}}). Plain text inputs fail validation.

4. Selection Constraint Logic (Min / Max Choices)

DoorDash: Governed by min_selection and max_selection integers nested within the modifier group schema.

Grubhub: Does not handle complex selections in the core item payload directly; it uses standalone, 
decoupled reference identifiers called modifier_prompts.

Uber Eats: Governed by a quantity_info nested block using min_permitted and max_permitted variables.

Architectural Divergence Summary
Specification Feature | DoorDash | Grubhub | Uber Eats
API Architecture | Hierarchical Tree | Normalized / Flat Table | Relational Graph Map
Price Format | Integer Cents (1299) | Decimal Float (12.99) | Integer Cents (1299)
Text Structure | Plain String | Plain String | Nested Translation Map
P360 Mapping Method | Hierarchy Builder (Deep) | Row Flattener / Target Split | Component / Object Map
Primary HTTP Verb | POST | POST | PUT
```

### Prompt 4: Branding Enhancement
```
branch this. Add a header page that has the summary, add Informatica Branding to it. Include anchor 
links to the main sections.
```

## Key Features

### Content Structure
- **Landing Page**: Executive summary with Informatica branding and navigation
- **Overview Section**: Challenge statement and context
- **API Architecture Differences**: Deep dive into technical platform differences
- **Menu Item Comparisons**: 4 menu items compared across all 3 platforms
  1. Customizable Burger
  2. Pizza with Toppings
  3. Build-Your-Own Salad
  4. Combo Meal Deal
- **MDM Solution Architecture**: Data flow diagram showing sources → MDM Hub → targets
- **Key Benefits**: Data consistency, operational efficiency, data quality, scalability
- **Summary**: Implementation notes and next steps

### Technical Highlights
- **Structural Design Models**: Hierarchical (DoorDash) vs. Normalized (Grubhub) vs. Relational (Uber Eats)
- **Pricing Formats**: Integer cents vs. decimal floats
- **Localization**: Plain text vs. translation maps
- **Selection Logic**: Different constraint implementations per platform

### Design Features
- Informatica brand colors (Orange #FF6C0C, Dark Blue #001F5F, Light Blue #00A1DF)
- Sticky navigation bar with section highlighting
- Smooth scrolling between sections
- Fully editable content (contenteditable="true")
- Image placeholders for later additions
- Print-friendly styling
- Responsive design

## Use Cases
- Sales presentations for QSR customers
- Technical demonstrations of MDM Hub capabilities
- Training material for Informatica P360 integrations
- Customer workshops on multi-platform data management
- Internal knowledge sharing on delivery platform APIs

## Deployment Options
1. **GitHub Gist**: https://gist.github.com/AlSommers-IFNA-SFDC/66bc684cb278fad1600b39d907cdb403
2. **GitHub Repository**: https://github.com/AlSommers-IFNA-SFDC/artifact-collateral
3. **Local File**: Open directly in any modern web browser
4. **GitHub Pages**: Enable Pages in repository settings for public URL

## Customization Guide
- Click any text element to edit content directly in browser
- Use "Save As" (Ctrl/Cmd+S) to save edited version
- Add images by replacing `[Add ... here]` placeholder divs
- Modify colors by editing CSS variables in `<style>` section
- Add/remove sections by duplicating section blocks

## Technical Stack
- Pure HTML5/CSS3/JavaScript
- No external dependencies
- Self-contained single file
- Works offline
- Cross-browser compatible

## Version History
- **v1.0** - Initial creation with technical comparisons (2026-05-18)
- **v2.0** - Added Informatica branding and landing page (2026-05-18)

## Author
Created by Claude Sonnet 4.5 via Claude Code
Date: May 18, 2026

## License
Internal use - Informatica LLC
