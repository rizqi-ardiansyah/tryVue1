# Dashboard App

## Overview

This is a Vue 3 dashboard application built with modern web technologies. The project uses Vue 3 with TypeScript for the frontend framework, Vite as the build tool, and Tailwind CSS for styling. It includes Chart.js integration for data visualization capabilities, making it suitable for creating interactive dashboards with charts and analytics features. The application follows Vue 3 Composition API patterns and includes Vue Router for single-page application navigation.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: Vue 3 with Composition API and TypeScript for type safety and modern development patterns
- **Build Tool**: Vite for fast development server and optimized production builds
- **Routing**: Vue Router 4 for client-side navigation with lazy-loaded route components
- **Styling**: Tailwind CSS 4 for utility-first styling with Tailwind Typography plugin for enhanced text formatting

### Development Tooling
- **Type Checking**: TypeScript with strict configuration and Vue-specific type support via vue-tsc
- **Code Quality**: ESLint with Vue and TypeScript configurations for code linting
- **Code Formatting**: Prettier for consistent code formatting with custom rules (no semicolons, single quotes, 100 character line width)
- **Development Experience**: Vue DevTools plugin for enhanced debugging and development workflow

### Data Visualization
- **Charting Library**: Chart.js 4 integrated through vue-chartjs for creating interactive charts and graphs
- **Chart Types**: Support for various chart types suitable for dashboard analytics and data presentation

### Project Structure
- **Path Aliases**: Uses `@/*` alias pointing to `src/*` for clean import statements
- **Component Organization**: Standard Vue project structure with views, components, and router separation
- **Asset Management**: Centralized CSS assets with base styles and Tailwind integration

### Browser Compatibility
- **Target Environment**: Modern browsers with ES modules support
- **Development Server**: Configured to run on host `0.0.0.0` port 5000 for accessibility in containerized environments

## External Dependencies

### Core Dependencies
- **Vue 3** (^3.5.18): Main frontend framework
- **Vue Router** (^4.5.1): Client-side routing solution
- **Chart.js** (^4.5.0): Data visualization library
- **vue-chartjs** (^5.3.2): Vue 3 wrapper for Chart.js integration

### Styling Dependencies
- **Tailwind CSS** (^4.1.13): Utility-first CSS framework
- **@tailwindcss/typography** (^0.5.16): Typography plugin for enhanced text styling
- **Autoprefixer** (^10.4.21): CSS vendor prefix automation

### Development Dependencies
- **Vite** (^7.0.6): Build tool and development server
- **TypeScript** (~5.8.0): Type checking and compilation
- **ESLint** (^9.31.0): Code linting with Vue and TypeScript support
- **Prettier** (3.6.2): Code formatting
- **Vue DevTools** (^8.0.0): Development debugging tools

### Runtime Environment
- **Node.js**: Requires Node.js ^20.19.0 or >=22.12.0
- **Package Manager**: Uses npm with package-lock.json for dependency management