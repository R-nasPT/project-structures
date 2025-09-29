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
│   │   ├── routes.tsx
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
Each feature is self-contained with its own components, hooks, API calls, and types. This makes features easier to maintain, test, and potentially extract into separate packages.

### 2. **Clear Separation of Concerns**
- **`app/`** - Application-level configuration and providers
- **`features/`** - Business logic organized by domain
- **`shared/`** - Reusable code that doesn't belong to any specific feature

### 3. **Consistent Folder Structure**
Every feature follows the same internal structure:
- `components/` - Feature-specific UI components
- `pages/` - Route components for this feature
- `hooks/` - Custom hooks for business logic
- `api/` - API calls related to this feature
- `types.ts` - TypeScript types for this feature

## 📝 File Examples

### Route Configuration (`app/routes/index.tsx`)
```typescript
import { createBrowserRouter } from 'react-router-dom';
import { Layout } from '@/shared/components/layout/Layout';
import { ProtectedRoute } from './ProtectedRoute';

// Lazy load pages for better performance
const LoginPage = lazy(() => import('@/features/auth/pages/LoginPage'));
const DashboardPage = lazy(() => import('@/features/dashboard/pages/DashboardPage'));
const ProductsPage = lazy(() => import('@/features/products/pages/ProductsPage'));

export const router = createBrowserRouter([
  {
    path: '/',
    element: <Layout />,
    children: [
      {
        path: '/login',
        element: <LoginPage />
      },
      {
        path: '/dashboard',
        element: (
          <ProtectedRoute>
            <DashboardPage />
          </ProtectedRoute>
        )
      },
      {
        path: '/products',
        element: (
          <ProtectedRoute>
            <ProductsPage />
          </ProtectedRoute>
        )
      }
    ]
  }
]);
```

### Feature Hook Example (`features/products/hooks/useProducts.ts`)
```typescript
import { useQuery } from '@tanstack/react-query';
import { productsApi } from '../api/products.api';
import { Product } from '../types';

export const useProducts = () => {
  return useQuery({
    queryKey: ['products'],
    queryFn: productsApi.getAll,
    staleTime: 5 * 60 * 1000, // 5 minutes
  });
};

export const useProduct = (id: string) => {
  return useQuery({
    queryKey: ['products', id],
    queryFn: () => productsApi.getById(id),
    enabled: !!id,
  });
};
```

### API Layer Example (`features/products/api/products.api.ts`)
```typescript
import { apiClient } from '@/shared/utils/api/client';
import { Product, CreateProductDto, UpdateProductDto } from '../types';

export const productsApi = {
  getAll: (): Promise<Product[]> => 
    apiClient.get('/products').then(res => res.data),
  
  getById: (id: string): Promise<Product> => 
    apiClient.get(`/products/${id}`).then(res => res.data),
  
  create: (data: CreateProductDto): Promise<Product> => 
    apiClient.post('/products', data).then(res => res.data),
  
  update: (id: string, data: UpdateProductDto): Promise<Product> => 
    apiClient.put(`/products/${id}`, data).then(res => res.data),
  
  delete: (id: string): Promise<void> => 
    apiClient.delete(`/products/${id}`)
};
```

## 🚀 Benefits

### ✅ **Scalability**
- Easy to add new features without affecting existing code
- Clear boundaries between different parts of the application
- Simple to onboard new team members

### ✅ **Maintainability**
- Related code is grouped together
- Easy to locate and modify specific functionality
- Consistent patterns across the entire codebase

### ✅ **Testability**
- Each feature can be tested in isolation
- Shared utilities are easily mockable
- Clear separation makes unit testing straightforward

### ✅ **Code Reusability**
- Shared components and hooks prevent duplication
- Features can be easily extracted or reused
- Common patterns are centralized

## 🎨 Naming Conventions

### Files and Folders
- Use **PascalCase** for component files: `ProductCard.tsx`
- Use **camelCase** for utility files: `formatDate.ts`
- Use **kebab-case** for folders: `user-profile/`
- Use **UPPER_CASE** for constants: `API_ENDPOINTS`

### Components and Hooks
- Components: `ProductCard`, `UserProfile`
- Hooks: `useProducts`, `useAuth`
- Pages: `ProductsPage`, `LoginPage`
- Contexts: `AuthProvider`, `ThemeProvider`

## 📚 Additional Tips

### Import Organization
```typescript
// External libraries
import React from 'react';
import { useNavigate } from 'react-router-dom';

// Internal shared modules
import { Button } from '@/shared/components/ui/Button';
import { useDebounce } from '@/shared/hooks';

// Feature-specific imports
import { useProducts } from '../hooks/useProducts';
import { ProductCard } from '../components/ProductCard';

// Types
import type { Product } from '../types';
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

This structure provides a solid foundation for building scalable React applications with React Router while maintaining clean code organization and developer productivity.
