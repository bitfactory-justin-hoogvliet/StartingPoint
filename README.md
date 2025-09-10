# Dream African Adventures - Travel Form Application

A professional Vue.js one-page application for a travel agency specializing in African adventures. Features smooth auto-scrolling bridges between form sections with immersive imagery and engaging content, styled with Charlie's Travels professional aesthetic and BVB tribute layout structure.

## Features

- 🎨 **Professional Design**: Clean, sophisticated styling inspired by Charlie's Travels
- 📱 **Responsive Design**: Works perfectly on desktop, tablet, and mobile
- 🎭 **Mixed Input Types**: Text inputs and clickable visual elements
- 🌉 **Manual-progression Bridges**: Compact, professional content sections between forms
- 🎯 **Auto-jumping Navigation**: Click buttons and page automatically scrolls to next section
- 🎨 **Alternating Themes**: Light and dark bridge sections for visual variety
- 🖼️ **African Imagery**: Beautiful travel photography from the images folder
- 🎯 **Streamlined Experience**: Simple start with just name collection initially

## Form Sections

1. **Personal Information**: Name only (streamlined start)
2. **Travel Preferences**: Clickable destination cards (South Africa, Kenya, Tanzania, Botswana, Namibia, Zambia)
3. **Budget & Timeline**: Date selection and budget ranges with visual cards
4. **Travel Style**: Adventure, luxury, cultural, photography, family-friendly, romantic options

## Bridge Content

Each bridge section features:
- Stunning African landscape photography in a compact, professional layout
- Concise, informative text about African travel experiences
- Manual progression with "Continue Journey" buttons
- **Automatic page scrolling/jumping** - no manual scrolling required
- Alternating light and dark themes for visual variety
- Charlie's Travels-inspired clean, professional design

## Getting Started

### Prerequisites

- Node.js (v14 or higher)
- npm or yarn

### Installation

1. Install dependencies:
   ```bash
   npm install
   ```

2. Start the development server:
   ```bash
   npm run dev
   ```

3. Open your browser to `http://localhost:3000`

### Build for Production

```bash
npm run build
```

## Project Structure

```
src/
├── App.vue                 # Main application component
├── main.js                # Application entry point
├── style.css              # Global styles
└── components/
    ├── FormSection.vue    # Reusable form section component
    └── BridgeSection.vue  # Auto-scrolling bridge component
```

## Customization

- **Images**: Replace files in the `images/` folder with your own African travel photography
- **Colors**: Modify the professional color scheme using CSS custom properties in `style.css` (primary: forest green, accent: warm gold)
- **Content**: Update bridge text content in `App.vue` data
- **Destinations**: Add or modify travel destinations in the destinations array
- **Timing**: Adjust auto-scroll timing in `BridgeSection.vue`

## Technologies Used

- Vue.js 3 (Composition API)
- Vite (Development server)
- CSS3 (Grid, Flexbox, Animations)
- Font Awesome (Icons)
- Inter Font (Typography)

## Browser Support

- Chrome/Edge 88+
- Firefox 85+
- Safari 14+

---

Created with ❤️ for African adventure seekers
