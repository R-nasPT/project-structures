# React.js + React Router Project Structure

> A scalable, enterprise-grade folder structure for React applications using React Router with modern patterns

## 📁 Recommended Structure

```
src/
├── core/                                  # 🏗️ Core app infrastructure
│   ├── layout/                            # 📐 App layout components
│   │   ├── RootLayout.tsx
│   │   ├── Header/
│   │   ├── Sidebar/
│   │   ├── Footer/
│   │   └── index.ts
│   ├── store/                             # 🗄️ Global state management
(Redux)
│   │   ├── index.ts
│   │   ├── rootReducer.ts
│   │   └── middlewares.ts
(Zustand)
│   │   ├── useAppStore.ts
│   │   └── index.ts
│   ├── router/                            # 🧭 Router configuration
│   │   ├── index.tsx                      # Route definitions
│   │   ├── routes.ts
│   │   ├── guards/                        # 🛡️ Route protection
│   │   │   ├── ProtectedRoute.tsx         # 🔒 Auth protection wrapper
│   │   │   ├── RouteGuards.tsx
│   │   │   ├── AuthGuard.tsx
│   │   │   ├── RoleGuard.tsx
│   │   │   ├── GuestRoute.tsx             # 🚪 (optional) For pages that cannot be accessed after logging in, such as LoginPage
│   │   │   └── AdminRoute.tsx             # 🔒 (optional) สำหรับ role-based
│   │   └── loaders/                       # 📥 Data pre-fetching
│   │   │   ├── dashboardLoader.ts
│   │   │   ├── userLoader.ts
│   │   │   └── settingsLoader.ts
│   └── providers/                         # 🔧 App-wide providers
│       ├── QueryProvider.tsx
│       ├── ThemeProvider.tsx
│       └── AuthProvider.tsx
│
├── features/                              # 🎯 Feature-based modules
│   ├── auth/                              # 🔐 Authentication feature
│   │   ├── components/
│   │   │   ├── LoginForm.tsx
│   │   │   ├── SignupForm.tsx
│   │   │   └── index.ts
│   │   ├── hooks/
│   │   │   ├── useAuth.ts
│   │   │   └── useLogin.ts
│   │   ├── schemas/                       # 📋 Validation schemas
│   │   │   ├── login.schema.ts
│   │   │   ├── register.schema.ts
│   │   │   └── index.ts
│   │   ├── services/
│   │   │   ├── auth.service.ts
│   │   │   └── index.ts
│   │   ├── store/
│   │   │   ├── useAuthStore.ts
│   │   │   ├── authSlice.ts
│   │   │   └── index.ts
│   │   ├── types/
│   │   │   ├── auth.types.ts
│   │   │   └── index.ts
│   │   └── routes.ts
│   │
│   ├── dashboard/                         # 📊 Dashboard feature
│   │   ├── components/
│   │   ├── hooks/
│   │   ├── helpers/
│   │   ├── services/
│   │   ├── store/
│   │   ├── types/
│   │   └── routes.ts
│   │
│   ├── user-management/                   # 👥 User management feature
│   │   ├── components/
│   │   ├── constansts/
│   │   ├── hooks/
│   │   ├── services/
│   │   ├── store/
│   │   ├── types/
│   │   └── routes.ts
│   │
│   └── settings/                          # ⚙️ App Settings feature
│       ├── components/
│       ├── hooks/
│       ├── services/
│       ├── schemas/
│       ├── types/
│       └── routes.ts
│
├── shared/                                # 🔄 Reusable components and utilities
│   ├── components/
│   │   ├── ui/                            # 🧱 Basic UI building blocks - Reusable everywhere
│   │   │   ├── button/
│   │   │   │   ├── Button.tsx
│   │   │   │   ├── Button.test.tsx
│   │   │   │   ├── Button.types.tsx
│   │   │   │   └── index.ts
│   │   │   ├── input/
│   │   │   │   ├── Input.tsx
│   │   │   │   ├── Input.test.tsx
│   │   │   │   ├── Input.types.tsx
│   │   │   │   └── index.ts
│   │   │   ├── select/
│   │   │   ├── checkbox/
│   │   │   ├── modal/
│   │   │   ├── badge/
│   │   │   ├── card/
│   │   │   ├── textarea/
│   │   │   ├── switch/
│   │   │   ├── breadcrumb/
│   │   │   └── index.ts
│   │   ├── composite/                     # 🔗 Combined UI components - Enhanced functionality
│   │   │   ├── search-box/
│   │   │   │   ├── SearchBox.tsx
│   │   │   │   ├── SearchBox.test.tsx
│   │   │   │   ├── SearchBox.types.tsx
│   │   │   │   └── index.ts
│   │   │   ├── file-upload/
│   │   │   │   ├── FileUpload.tsx
│   │   │   │   ├── FileUpload.test.tsx
│   │   │   │   ├── FileUpload.types.tsx
│   │   │   │   └── index.ts
│   │   │   ├── filter-bar/
│   │   │   ├── date-picker/
│   │   │   ├── confirm-dialog/
│   │   │   └── index.ts
│   │   ├── widgets/                       # 🎯 Purpose-specific components - Business logic included (component เฉพาะจุดประสงค์)
│   │   │   ├── status-badge/
│   │   │   │   ├── StatusBadge.tsx
│   │   │   │   ├── StatusBadge.test.tsx
│   │   │   │   ├── StatusBadge.types.tsx
│   │   │   │   └── index.ts
│   │   │   ├── role-chip/                 # 🔐 Show user role + color + permission indicator
│   │   │   ├── currency-display/          # 💵 Show currency + format + symbol
│   │   │   ├── attachment-section/
│   │   │   ├── stat-card/                 # 📊 Show statistics + icon + trend + comparison
│   │   │   └── index.ts
│   │   ├── wrappers/                      # 📦 Layout containers - Structure and spacing
│   │   │   ├── section-panel/
│   │   │   │   ├── SectionPanel.tsx
│   │   │   │   ├── SectionPanel.test.tsx
│   │   │   │   ├── SectionPanel.types.tsx
│   │   │   │   └── index.ts
│   │   │   ├── page-header/
│   │   │   └── index.ts
│   │   └── common/                        # ⚡ Common utilities - States and notifications
│   │   │   ├── loading-spinner/
│   │   │   │   ├── LoadingSpinner.tsx
│   │   │   │   ├── LoadingSpinner.test.tsx
│   │   │   │   └── index.ts
│   │   │   ├── error-boundary/            # ⚠️ ไม่ค่อยจำเป็น
│   │   │   ├── error-fallback/
│   │   │   ├── not-found/
│   │   │   └── index.ts
│   │   └── index.ts                       # 📦 Export barrel
│   │
│   ├── constants/
│   │   ├── routes.constants.ts
│   │   ├── app.constants.ts
│   │   ├── roles.constants.ts
│   │   ├── regex.constants.ts             # ✍️ Regular expressions
│   │   ├── storage.constants.ts           # 🗝️ Keys for localStorage / sessionStorage
│   │   └── index.ts
│   │
│   ├── helpers/                           # 🛠️ Helper functions
│   │   ├── auth.helpers.ts
│   │   ├── business.helpers.ts
│   │   ├── api.helpers.ts                 # 🌐 API-related helpers
│   │   ├── ui.helpers.ts                  # 🎨 UI-specific helpers
│   │   └── index.ts
│   │
│   ├── hooks/                             # 🪝 Shared custom hooks
│   │   ├── useAnalytics.ts
│   │   ├── useCopyToClipboard.ts
│   │   ├── usePermissions.ts
│   │   └── index.ts
│   │
│   ├── lib/                               # 📚 Third-party configs
│   │   ├── axios.lib.ts
│   │   ├── icons.lib.ts 
│   │   ├── logger.lib.ts                  # 📝 Logging setup
│   │   └── index.ts
│   │
│   ├── schemas/                           # 📂 Shared data schemas (validation, API shapes, form structures)
│   │   ├── common.schema.ts
│   │   ├── api.schema.ts
│   │   ├── form.schema.ts
│   │   └── index.ts
│   │
│   ├── services/                          # 🔌 Shared services
│   │   ├── api/
│   │   │   ├── apiClient.ts
│   │   │   ├── endpoints.ts
│   │   │   ├── interceptors.ts
│   │   │   └── index.ts
│   │   ├── storage/
│   │   │   ├── localStorage.ts
│   │   │   ├── sessionStorage.ts
│   │   │   └── index.ts
│   │   └── index.ts
│   │
│   ├── store/                             # 🏪 Shared state stores
│   │   ├── useCommonStore.ts
│   │   ├── useCacheStore.ts
│   │   ├── useUIStore.ts
│   │   └── index.ts
│   │
│   ├── utils/                             # 🔧 Utility functions
│   │   ├── format.utils.ts
│   │   ├── date.utils.ts
│   │   └── index.ts
│   │
│   └── types/                             # 🧩 Shared TypeScript types
│       ├── api.types.ts
│       ├── common.types.ts
│       ├── env.types.ts
│       └── index.ts
│
├── pages/                                 # 📄 Route page components
│   ├── NotFoundPage.tsx                   # 🚫 404 error page
│   ├── ErrorPage.tsx                      # 💥 Global error page
│   ├── MaintenancePage.tsx
│   ├── auth/
│   │   ├── LoginPage.tsx
│   │   ├── SignupPage.tsx
│   │   └── AuthLayout.tsx
│   ├── dashboard/
│   │   ├── DashboardPage.tsx
│   │   └── DashboardLayout.tsx
│   ├── users/
│   │   ├── UsersPage.tsx
│   │   ├── UserDetailPage.tsx
│   │   └── UsersLayout.tsx
│   └── settings/
│       ├── SettingsPage.tsx
│       ├── SettingDetailPage.tsx
│       ├── SettingEditPage.tsx
│       └── SettingsLayout.tsx
│
├── assets/                                # 📁 Static assets
│   ├── images/
│   ├── icons/
│   ├── fonts/
│   └── videos/
│
├── config/                                # ⚙️ Configuration files
│   ├── env.config.ts
│   ├── database.config.ts
│   ├── theme.config.ts
│   └── index.ts
│
├── main.tsx                               # 🚀 App entry point
└── vite-env.d.ts                          # ⚡ Vite type definitions
```

## 🎯 Key Principles

### 1. **Feature-Based Organization**
Each feature is self-contained with its own components, hooks, services, and types. This makes features easier to maintain, test, and potentially extract into separate packages.

### 2. **Clear Separation of Concerns**
- **`core/`** - Application infrastructure (routing, layout, global state)
- **`features/`** - Business logic organized by domain
- **`shared/`** - Reusable code that doesn't belong to any specific feature
- **`pages/`** - Route components that compose features

### 3. **Component Hierarchy**
Components are organized by complexity and purpose:
- `ui/` - Basic building blocks (Button, Input)
- `composite/` - Combined components (SearchBox, FileUpload)
- `widgets/` - Business-logic components (StatusBadge, RoleChip)
- `wrappers/` - Layout containers (SectionPanel, PageHeader)
- `common/` - Utility components (LoadingSpinner, ErrorFallback)

### 4. **Consistent Folder Structure**
Every feature follows the same internal structure, making it predictable and easy to navigate.

## 📝 File Examples

### Application-wide layout structure that wraps all pages. (`core/layout/RootLayout.tsx`)
```tsx
import { Outlet } from 'react-router';
import { Header } from './Header';
import { Sidebar } from './Sidebar';

export default function RootLayout() {
  return (
    <div className="app">
      <Header />
      <div className="app-body">
        <Sidebar />
        <main className="content">
          <Outlet />
        </main>
      </div>
    </div>
  );
}
```

### Routing Configuration (`core/router/`)
```tsx
// core/router/guards/ProtectedRoute.tsx
import { Navigate, Outlet } from 'react-router';
import { useAuthStore } from '@/features/auth/store';

export function ProtectedRoute() {
  const isAuthenticated = useAuthStore((state) => state.isAuthenticated);

  if (!isAuthenticated) {
    return <Navigate to="/login" replace />;
  }

  return <Outlet />;
}
```
```typescript
// core/router/routes.ts
import type { RouteObject } from 'react-router';
import RootLayout from '@/core/layout/RootLayout';
import { ProtectedRoute } from './guards/ProtectedRoute';
import { authRoutes } from '@/features/auth/routes';
import { menuRoutes } from "@/features/mainMenu/routes";
import { dashboardRoutes } from '@/features/dashboard/routes';
import NotFoundPage from '@/pages/NotFoundPage';

export const routes: RouteObject[] = [
  {
    path: '/',
    Component: RootLayout,
    children: [
      ...authRoutes,
      ...menuRoutes,
      {
        path: '*',
        Component: NotFoundPage,
      },
    ],
  },
];
```
```tsx
// core/router/index.tsx
import { createBrowserRouter, RouterProvider } from 'react-router';
import { routes } from './routes';

const router = createBrowserRouter(routes);

export function AppRouter() {
  return <RouterProvider router={router} />;
}
```

---

## 🎯 Features - Business Logic Modules

Each feature is a self-contained module with all its dependencies.

### Standard Feature Structure

```
features/[feature-name]/
├── components/              # Feature-specific components
├── hooks/                   # Custom hooks for business logic
├── schemas/                 # Validation schemas (Zod/Yup)
├── services/                # API calls and external services
├── store/                   # Feature-specific state
├── types/                   # TypeScript definitions
├── constants/               # Feature-specific constants
├── helpers/                 # Feature-specific utilities
└── routes.ts                # Feature route definitions
```

---

## 🔄 Shared Resources

Reusable code that can be used across multiple features.

### `shared/components/` - Component Library

Components organized by complexity and purpose.

#### 🧱 `ui/` - Basic Building Blocks

Foundational UI components with no business logic.

```
ui/
├── button/
│   ├── Button.tsx
│   ├── Button.test.tsx
│   ├── Button.types.ts
│   └── index.ts
├── input/
├── modal/
├── badge/
└── textarea/
```

**Characteristics:**
* Pure UI components
* No business logic
* Highly reusable
* Accept only UI-related props

**Example:**
```tsx
// shared/components/ui/button/Button.tsx
import type { ButtonProps } from './Button.types';

export function Button({ 
  variant = 'primary', 
  size = 'md', 
  children,
  ...props 
}: ButtonProps) {
  return (
    <button 
      className={`btn btn-${variant} btn-${size}`}
      {...props}
    >
      {children}
    </button>
  );
}

// Usage
<Button variant="primary" size="lg">Click me</Button>
```

---

#### 🔗 `composite/` - Combined Components

Components that combine multiple UI elements with enhanced functionality.

```
composite/
├── search-box/              # Input + Icon + Clear button
├── file-upload/             # Input + Preview + Progress bar
├── filter-bar/              # Multiple filters + Sort + Search
├── date-picker/             # Input + Calendar popup
└── confirm-dialog/          # Modal + Message + Actions
```

**Characteristics:**
* Combines multiple UI components
* Has internal logic (debounce, validation)
* Still domain-agnostic
* Reusable across features

**Example:**
```tsx
// shared/components/composite/search-box/SearchBox.tsx
import { useState, useEffect } from 'react';
import { Input } from '@/shared/components/ui/input';
import { Button } from '@/shared/components/ui/button';
import type { SearchBoxProps } from './SearchBox.types';

export function SearchBox({ 
  onSearch, 
  debounce = 300,
  placeholder = 'Search...',
}: SearchBoxProps) {
  const [value, setValue] = useState('');

  useEffect(() => {
    const timer = setTimeout(() => {
      onSearch(value);
    }, debounce);

    return () => clearTimeout(timer);
  }, [value, debounce, onSearch]);

  return (
    <div className="search-box">
      <Input 
        value={value}
        onChange={(e) => setValue(e.target.value)}
        placeholder={placeholder}
      />
      {value && (
        <Button 
          variant="ghost" 
          onClick={() => setValue('')}
        >
          Clear
        </Button>
      )}
    </div>
  );
}

// Usage
<SearchBox 
  onSearch={handleSearch}
  debounce={500}
  placeholder="Search users..."
/>
```

---

#### 🎯 `widgets/` - Business Logic Components

Components with domain-specific business logic.

```
widgets/
├── status-badge/            # Badge with status colors & icons
├── role-chip/               # Chip with role permissions
├── currency-display/        # Formatted currency display
├── stat-card/               # Statistics with trends
└── attachment-section/      # File management widget
```

**Characteristics:**
* Contains business logic
* Domain-specific
* Understands data structure
* Smart components

**Example:**
```tsx
// shared/components/widgets/status-badge/StatusBadge.tsx
import { Badge } from '@/shared/components/ui/badge';
import type { StatusBadgeProps } from './StatusBadge.types';

const statusConfig = {
  pending: { color: 'yellow', icon: '⏳', label: 'Pending' },
  approved: { color: 'green', icon: '✓', label: 'Approved' },
  rejected: { color: 'red', icon: '✗', label: 'Rejected' },
};

export function StatusBadge({ status }: StatusBadgeProps) {
  const config = statusConfig[status];
  
  return (
    <Badge variant={config.color}>
      <span>{config.icon}</span>
      <span>{config.label}</span>
    </Badge>
  );
}

// Usage - automatically gets correct color, icon, label
<StatusBadge status="approved" />
```

```tsx
// shared/components/widgets/currency-display/CurrencyDisplay.tsx
import type { CurrencyDisplayProps } from './CurrencyDisplay.types';

const currencyConfig = {
  USD: { symbol: '$', locale: 'en-US' },
  EUR: { symbol: '€', locale: 'de-DE' },
  THB: { symbol: '฿', locale: 'th-TH' },
};

export function CurrencyDisplay({ 
  amount, 
  currency = 'USD' 
}: CurrencyDisplayProps) {
  const config = currencyConfig[currency];
  
  const formatted = new Intl.NumberFormat(config.locale, {
    style: 'currency',
    currency,
  }).format(amount);

  return <span className="currency">{formatted}</span>;
}

// Usage
<CurrencyDisplay amount={1234.56} currency="THB" />
// Output: ฿1,234.56
```

---

#### 📦 `wrappers/` - Layout Containers

Components for structuring and spacing content.

```
wrappers/
├── section-panel/           # Panel with header/footer
├── page-header/             # Page title + breadcrumb + actions
└── content-wrapper/         # Responsive container
```

**Example:**
```tsx
// shared/components/wrappers/section-panel/SectionPanel.tsx
import type { SectionPanelProps } from './SectionPanel.types';

export function SectionPanel({ 
  title, 
  actions,
  children 
}: SectionPanelProps) {
  return (
    <div className="section-panel">
      <div className="panel-header">
        <h2>{title}</h2>
        {actions && <div className="actions">{actions}</div>}
      </div>
      <div className="panel-body">
        {children}
      </div>
    </div>
  );
}

// Usage
<SectionPanel 
  title="User Details"
  actions={<Button>Edit</Button>}
>
  <UserForm />
</SectionPanel>
```

---

#### ⚡ `common/` - Utility Components

Common states and notifications.

```
common/
├── loading-spinner/
├── error-fallback/
├── not-found/
└── toast/
```

---

### 📊 Component Decision Tree

```
Need to create a component?
│
├─ Basic UI element? (Button, Input, Card)
│  └─ ✅ Place in ui/
│
├─ Combines multiple UI elements? (SearchBox, FileUpload)
│  └─ ✅ Place in composite/
│
├─ Has business logic? (StatusBadge, CurrencyDisplay)
│  └─ ✅ Place in widgets/
│
├─ Layout/Structure purpose? (Panel, PageHeader)
│  └─ ✅ Place in wrappers/
│
└─ Utility/State component? (Loading, Error)
   └─ ✅ Place in common/
```

---

## 🚀 Benefits

### ✅ **Scalability**
- Easy to add new features without affecting existing code
- Clear boundaries between different parts of the application
- Features can be developed independently
- Simple to extract features into separate packages

### ✅ **Maintainability**
- Related code is grouped together
- Easy to locate and modify specific functionality
- Consistent patterns across the entire codebase
- Self-documenting structure

### ✅ **Testability**
- Each feature can be tested in isolation
- Shared utilities are easily mockable
- Clear separation makes unit testing straightforward
- Components have single responsibility

### ✅ **Code Reusability**
- Shared components and hooks prevent duplication
- Features can be easily extracted or reused
- Common patterns are centralized
- Component hierarchy promotes composition

### ✅ **Developer Experience**
- New team members can quickly understand the structure
- IDE auto-completion works better with clear paths
- Predictable file locations
- Consistent naming reduces cognitive load

## 🎨 Naming Conventions

### Files and Folders
- Use **PascalCase** for component files: `ProductCard.tsx`
- Use **camelCase** for utility files: `formatDate.ts`
- Use **kebab-case** for folders: `user-profile/`
- Use **UPPER_CASE** for constants: `API_ENDPOINTS`

### Components and Hooks
* **Components**: `ProductCard`, `UserProfile`, `StatusBadge`
* **Pages**: `ProductsPage`, `LoginPage`, `DashboardPage`
* **Hooks**: `useProducts`, `useAuth`, `useDebounce`
* **Contexts**: `AuthProvider`, `ThemeProvider`
* **Services**: `authService`, `userService`, `productService`
* **Utils**: `formatDate`, `capitalizeString`, `calculateTotal`

## 📚 Additional Tips

### Import Organization
```tsx
// 1. External libraries
import { useState, useEffect } from 'react';
import { useQuery } from '@tanstack/react-query';

// 2. Internal absolute imports - grouped by source
import { Button } from '@/shared/components/ui/button';
import { SearchBox } from '@/shared/components/composite/search-box';
import { useDebounce } from '@/shared/hooks';

// 3. Feature imports
import { useUsers } from '@/features/user-management/hooks';
import { userService } from '@/features/user-management/services';

// 4. Types
import type { User } from '@/features/user-management/types';

// 5. Relative imports (avoid when possible)
import { UserCard } from './UserCard';
```

### Barrel Exports
Use `index.ts` files to create clean import paths:
```typescript
// features/products/components/index.ts
export { ProductCard } from './ProductCard';
export { ProductList } from './ProductList';
export { ProductForm } from './ProductForm';

// Usage
import { ProductCard, ProductList } from '@/features/products/components';
```

---

## 🎉 Conclusion

This structure provides a solid foundation for building scalable React applications. Key takeaways:

* **Feature-based** organization keeps related code together
* **Clear hierarchy** for components (ui → composite → widgets → wrappers)
* **Separation of concerns** between core, features, shared, and pages
* **Consistent patterns** make the codebase predictable
* **Type safety** throughout with TypeScript
* **Easy to maintain** and extend as the app grows

Remember: This structure is a guideline, not a rigid rulebook. Adapt it to your team's needs and project requirements.

**Happy coding! 🚀**
