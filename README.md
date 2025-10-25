# Localist

A platform for discovering local venues, events, and experiences.

## Project Structure

This repository contains two main components as git submodules:

- **localist-frontend**: Next.js frontend application
- **localist-backend**: Node.js/TypeScript backend API

## Getting Started

### Clone with Submodules

To clone this repository with all submodules:

```bash
git clone --recurse-submodules git@github.com:l3ocifer/localist.git
```

If you've already cloned the repository without submodules:

```bash
git submodule update --init --recursive
```

### Working with Submodules

Each submodule is a separate git repository and can be worked on independently:

```bash
# Navigate to a submodule
cd localist-frontend

# Make changes, commit, and push as normal
git add .
git commit -m "Your changes"
git push
```

### Updating Submodules

To update all submodules to their latest commits:

```bash
git submodule update --remote
```

Then commit the submodule pointer updates in the main repository:

```bash
git add .
git commit -m "Update submodules"
git push
```

## Development

See the README in each submodule for specific development instructions:

- [Frontend README](./localist-frontend/README.md)
- [Backend README](./localist-backend/README.md)

## Repository Links

- Main: https://github.com/l3ocifer/localist
- Frontend: https://github.com/l3ocifer/localist-frontend
- Backend: https://github.com/l3ocifer/localist-backend

