# AI Front End Manager

An AI-powered front-end manager for maintaining and developing a personal website. This project uses git submodules to manage the website repository and Firebase for hosting.

## Project Structure

```
.
├── .git/                 # Git repository data
├── .gitignore           # Git ignore rules
├── website_repo/        # Personal website submodule
│   ├── dist/           # Production build output
│   ├── src/            # Source code
│   ├── firebase.json   # Firebase configuration
│   └── .firebaserc     # Firebase project settings
├── README.md           # This file
└── ToDoLog.md          # Task tracking
```

## Setup Instructions

### Prerequisites
- Git (version 2.x or higher)
- Node.js (version 18.x or higher)
- npm (version 6.x or higher)
- Firebase CLI (for deployment)
- nvm (recommended for Node.js version management)

### Initial Setup

1. Clone this repository:
```bash
git clone https://github.com/kosakoytim/ai-front-end-manager-hacspace.git
cd ai-front-end-manager-hacspace
```

2. Initialize and update the submodule:
```bash
git submodule init
git submodule update
```

3. Set up Node.js environment:
```bash
# Using nvm
nvm install 18
nvm use 18

# Install Firebase CLI
npm install -g firebase-tools
```

### Working with the Website Submodule

The website code is managed as a git submodule in the `website_repo` directory. Here are common operations:

#### Updating the Submodule
To get the latest changes from the website repository:
```bash
git submodule update --remote website_repo
```

#### Making Changes
1. Navigate to the submodule directory:
```bash
cd website_repo
```

2. Make your changes and commit them:
```bash
git add .
git commit -m "Your commit message"
git push
```

3. Update the main repository to track the new submodule commit:
```bash
cd ..
git add website_repo
git commit -m "Update website submodule"
git push
```

### Deployment Process

1. **Prepare for deployment**:
```bash
cd website_repo
npm install
```

2. **Build the project**:
```bash
npm run build
```

3. **Deploy to Firebase**:
```bash
firebase login
firebase deploy --only hosting
```

4. **Verify deployment** at https://timmyksky.web.app

## Development Guidelines

1. Always work on feature branches
2. Keep the submodule and main repository in sync
3. Follow the commit message conventions:
   - feat: New features
   - fix: Bug fixes
   - refactor: Code refactoring
   - docs: Documentation updates
4. Update documentation as needed
5. Test deployment locally before pushing to production

## Task Management

- Current tasks and their status are tracked in `ToDoLog.md`
- New tasks should be added to the appropriate section in `ToDoLog.md`
- Completed tasks should be marked with [x]
- Each major change should update both READMEs (main and website)

## Recent Changes

- Updated blog section with modern card layout and responsive design
- Implemented consistent styling across blog cards
- Added section title "B L O G S" with proper styling
- Improved image handling with aspect ratio and hover effects
- Fixed responsive layout for different screen sizes
- Updated documentation for blog section management
- Successfully deployed changes to Firebase hosting

## Pending Improvements

- Migrate from @import to @use/@forward in Sass files
- Implement lazy loading for blog images
- Automated deployment workflow
- CI/CD pipeline implementation
- Development guidelines enhancement
- Testing environment setup
- Development tools and linters configuration

## Contact

For questions or issues, please contact the repository maintainers.

## Blog Section

The blog section displays a grid of blog cards, each showcasing a blog post with an image, title, date, and description. The layout is responsive and adapts to different screen sizes:

- Desktop: 3 cards per row
- Tablet: 2 cards per row
- Mobile: 1 card per row

### Blog Card Components

Each blog card includes:
- Featured image (4:3 aspect ratio)
- Title (truncated to 2 lines)
- Date (formatted as dd/MM/YYYY)
- Description (truncated to 3 lines)

### Adding Blog Posts

Blog posts are stored in Firebase. Each blog post should have the following structure:

```javascript
{
  title: string,
  description: string,
  imageUrl: string,
  timestamp: number (Unix timestamp),
  content: string (HTML content)
}
```

### Styling

Blog cards feature hover effects and consistent spacing:
- Card shadow on hover
- Image zoom effect on hover
- Consistent margins between cards (2rem on mobile, 3rem on desktop)
- Section title "B L O G S" centered above the grid 