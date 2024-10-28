## FOLDER STRUCTURE

```
my-app/
├── public/                      # Static assets like images, icons, videos, etc.
│   ├── icons/
│   ├── images/
│   └── videos/
├── src/                         # Source folder
│   ├── app/                     # Next.js App Router directory
│   │   ├── (auth)/              # Route grouping for authentication (login, signup)
│   │   │   ├── layout.js        # Layout for auth pages
│   │   │   └── login/           # Login page
│   │   ├── (dashboard)/         # Route grouping for dashboard (can use custom layouts here)
│   │   │   ├── layout.js        # Dashboard layout
│   │   │   ├── page.js          # Main dashboard page
│   │   │   ├── camera/          # Camera-specific routes
│   │   │   │   ├── page.js      # Camera management page
│   │   │   │   └── [cameraId]/  # Dynamic route for individual camera views
│   │   │   ├── reports/         # Report-related routes
│   │   │   │   ├── page.js      # Reports page
│   │   │   │   └── [reportId]/  # Dynamic route for individual report details
│   │   │   ├── settings/        # Settings pages (user, application settings)
│   │   │   │   └── page.js      # Main settings page
│   │   └── api/                 # API routes (internal APIs)
│   │       ├── auth/            # Authentication APIs
│   │       ├── notifications/   # Notification-related APIs
│   │       └── reports/         # Report generation APIs
│   ├── components/              # Reusable UI components
│   │   ├── common/              # Common UI elements like buttons, modals
│   │   ├── camera/              # Camera-related components (preview, controls, etc.)
│   │   ├── dashboard/           # Dashboard components (widgets, charts, etc.)
│   │   └── notifications/       # Notification components
│   ├── contexts/                # React contexts (AuthContext, CameraContext, etc.)
│   ├── features/                # Feature-based modular structure
│   │   ├── camera/              # Camera management feature
│   │   │   ├── hooks/           # Custom hooks specific to camera features
│   │   │   ├── api/             # API calls related to camera features
│   │   │   ├── components/      # Feature-specific components (if not already in components folder)
│   │   │   └── utils/           # Utility functions for cameras
│   │   ├── notifications/       # Real-time alerts and notifications
│   │   │   ├── hooks/
│   │   │   ├── api/
│   │   │   └── components/
│   │   └── reports/             # Reporting feature
│   │       ├── hooks/
│   │       ├── api/
│   │       └── components/
│   ├── hooks/                   # Shared hooks (useAuth, useRole, etc.)
│   ├── layouts/                 # Global or shared layouts
│   │   ├── AdminLayout.js       # Layout for the admin panel
│   │   ├── UserLayout.js        # Layout for standard user views
│   ├── services/                # External API integrations, notifications, etc.
│   │   ├── auth.js              # Authentication services
│   │   ├── notification.js      # WhatsApp, email notifications
│   │   └── reports.js           # Report services
│   ├── store/                   # Global state (Redux, Zustand)
│   ├── styles/                  # Global styles, CSS modules, or SCSS files
│   │   ├── globals.css
│   │   ├── dashboard.module.css
│   │   └── components/
│   └── utils/                   # Utility functions (helpers, constants, validation)
│       ├── auth.js
│       ├── constants.js
│       └── dateUtils.js
└── tests/                       # Testing (Jest, Cypress)
    ├── components/
    ├── features/
    └── pages/
```

### Explanation of Key Folders:
- **app/**: The new App Router directory contains all pages, APIs, and route groups. Key sections include `api` for API endpoints, `(auth)` for authentication pages, and `(dashboard)` for the main dashboard and related features.
- **components/**: Houses reusable UI components organized by purpose (e.g., `dashboard`, `camera`, `notifications`), promoting easy reuse across features.
- **features/**: Modular feature-first design; each feature (like `camera`, `notifications`, `reports`) is self-contained with its specific hooks, components, and utilities.
- **store/**: State management to keep global state organized and accessible, especially for complex or cross-feature state handling.
- **services/**: External API integrations like WhatsApp or email notifications are managed here to centralize third-party dependencies.
- **utils/**: Common utilities like date formatting, validation, and constants are centralized here to avoid redundancy.
