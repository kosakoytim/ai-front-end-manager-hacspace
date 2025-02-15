# AI Front End Manager

An AI-powered front-end manager for maintaining and developing a personal website. This project uses git submodules to manage the website repository.

## Project Structure

```
.
├── .git/                 # Git repository data
├── .gitignore           # Git ignore rules
├── website_repo/        # Personal website submodule
├── README.md            # This file
└── ToDoLog.md          # Task tracking
```

## Setup Instructions

### Prerequisites
- Git (version 2.x or higher)
- Node.js and npm (for website development)

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

## Development Guidelines

1. Always work on feature branches
2. Keep the submodule and main repository in sync
3. Follow the commit message conventions
4. Update documentation as needed

## Task Management

- Current tasks and their status are tracked in `ToDoLog.md`
- New tasks should be added to the appropriate section in `ToDoLog.md`

## Contact

For questions or issues, please contact the repository maintainers. 