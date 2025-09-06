# Overview

This is a 3D bridge design and visualization application built with React Three Fiber. The application allows users to view, interact with, and analyze bridge components in a 3D environment with various viewing modes (perspective, plan, front, side elevations). It features component selection, material property display, dimensional annotations, and parametric bridge geometry.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture

**React + Three.js Stack**: The application uses React with React Three Fiber (@react-three/fiber) for 3D rendering, providing a declarative approach to Three.js scene management. Additional Three.js utilities from @react-three/drei handle camera controls, HTML overlays, and scene helpers.

**Component-Based UI**: The interface is built using Radix UI components with Tailwind CSS for styling, providing a modern, accessible design system. Key UI components include view controls, component trees, material properties panels, and dimension annotations.

**State Management**: Uses Zustand for lightweight state management, particularly for game/interaction states and audio controls. Component state is managed locally with React hooks for bridge parameters and UI interactions.

**3D Scene Organization**: The bridge model is organized into logical components (slab, abutments) with interactive selection, hover states, and dynamic camera positioning based on view modes.

## Backend Architecture

**Express.js Server**: Minimal Express.js backend with TypeScript support, configured for both development (with Vite middleware) and production builds. The server structure is prepared for REST API expansion with modular route organization.

**Storage Abstraction**: Implements a storage interface pattern with both in-memory (MemStorage) and database-ready implementations. Currently includes basic user management schema as a foundation for future authentication features.

**Development Setup**: Uses Vite for frontend development with hot module replacement, TypeScript compilation, and asset handling including 3D models and audio files.

## Data Architecture

**Bridge Geometry System**: Parametric bridge design with configurable dimensions (span, width, thickness, abutment properties) stored in custom hooks. Geometry calculations handle volume, positioning, and dimension annotations dynamically.

**Schema Definition**: Uses Drizzle ORM with PostgreSQL dialect for type-safe database operations. Includes Zod validation schemas for data integrity.

**3D Asset Pipeline**: Configured to handle various 3D file formats (GLTF, GLB) and audio files (MP3, OGG, WAV) with proper asset bundling through Vite.

## External Dependencies

**Database**: PostgreSQL with Neon Database serverless driver (@neondatabase/serverless) for scalable cloud database operations.

**3D Graphics**: Three.js ecosystem including React Three Fiber for React integration, Drei for utilities, and postprocessing for visual effects.

**UI Framework**: Extensive Radix UI component library providing accessible, unstyled components with Tailwind CSS for rapid styling.

**Development Tools**: Drizzle Kit for database migrations, TSX for TypeScript execution, and ESBuild for production bundling.

**State & Data**: TanStack React Query for server state management, Zustand for client state, and react-hook-form with Zod for form validation.

**Styling**: Tailwind CSS with class-variance-authority for component variants and clsx for conditional styling.