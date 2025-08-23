# 🧪 Frontend Engineer — Technical Assessment

**Deadline**: 2 days  
**Mode**: Submit code via GitHub repository

---

## 🎯 What You're Building

You're building an admin dashboard for Vidinfra's CDN management platform. Users need to monitor their content distributions and quickly find specific ones through filtering and search.

Your task is to create a responsive data table component that fetches and displays CDN distributions with proper pagination, filtering, and sorting capabilities.

---
**Design Reference**: [Figma Design](https://www.figma.com/design/7BATDXvcws9kJ1ghQcw9qX/Design-Task?node-id=15704-58520&t=5ODh14VS1hJFDR2r-1)

## 🛠 Tech Stack

* **Next.js 15** (App Router)
* **TypeScript**
* **Axios** for API calls
* **@tanstack/react-query** for data fetching
* **@tanstack/react-table** for table functionality
* **shadcn/ui** for UI components
* **nuqs**  for URL state management

---

## 📋 Core Requirements

### Data Table Features
* Pagination & column sorting  with page and limit controls
* Responsive design that works on mobile and desktop
* Loading states and error handling
* Empty state when no data is found

### Filtering System
* **CNAME filter**: Text input with debounced search
* **status filter**: Dropdown with options (active, inactive, pending)
* **Date range filter**: From/to date picker for created_at field
* All filters must persist in URL parameters

### Display Columns
* Label
* CNAME
* Origin
* Status (with status badges/colors)
* Created At (formatted date)

### Technical Requirements
* Use TypeScript with proper type definitions
* Implement proper error boundaries
* Follow accessibility best practices
* Clean, readable code structure

---

## 🌟 Nice-to-Have Features

* Skeleton loading states during data fetch
* Advanced empty states with helpful messaging
---

## 📡 API Information

**Base URL**: `https://api-staging.tenbyte.io/cdn`

**Endpoint**: `GET /distributions`

## Endpoint

    GET /v1/distributions

------------------------------------------------------------------------

## Query Parameters

### 📑 Pagination

  ----------------------------------------------------------------------------
  Parameter   Type     Description
  ----------- -------- -------------------------------------------------------
  `page`      number   Page number (default: 1)

  `limit`     number   Number of items per page (default: 15, min: 1, max: 50)
  ----------------------------------------------------------------------------

------------------------------------------------------------------------

### 🔍 Filtering

You can filter by the following fields:

-   `id`
-   `name`
-   `cname`
-   `domain`
-   `status`
-   `domain_type`
-   `cache_strategy`
-   `organization_id`
-   `certificate_id`
-   `enable_ssl`
-   `is_redirect_http_to_https`
-   `is_http2`
-   `is_http3`
-   `is_cname_valid`
-   `is_acme_challenge_valid`
-   `le_issue`
-   `created_at`
-   `updated_at`

#### Operators

  Operator        Description
  --------------- ------------------------------------------
  `eq`            Equals
  `ne`            Not equals
  `like`          Contains (case insensitive)
  `not-like`      Does not contain
  `starts-with`   Starts with
  `ends-with`     Ends with
  `gt`            Greater than
  `gte`           Greater than or equal
  `lt`            Less than
  `lte`           Less than or equal
  `in`            In list (comma-separated)
  `not-in`        Not in list
  `null`          Is null
  `not-null`      Is not null
  `between`       Between two values (comma-separated)
  `not-between`   Not between two values (comma-separated)

#### Example Filters

    filter[name][starts-with]=cdn-
    filter[status][in]=active,disabled
    filter[enable_ssl][eq]=true
    filter[created_at][between]=2025-01-01,2025-08-01

------------------------------------------------------------------------

### ↕ Sorting

  ---------------------------------------------------------------------------
  Parameter   Description
  ----------- ---------------------------------------------------------------
  `sort`      Sort fields. Prefix with `-` for descending. Allowed:
              `created_at`, `updated_at`, `name`, `status`, `domain_type`,
              `cache_strategy`, `domain`, `cname`

  ---------------------------------------------------------------------------

#### Example Sorts

    sort=-created_at
    sort=name
    sort=-created_at,name

------------------------------------------------------------------------

## 🚀 Getting Started

1. Create a new Next.js 15 project with TypeScript
2. Install required dependencies
3. Set up shadcn/ui components
4. Build the data table component
5. Implement filtering and pagination
6. Add responsive design
7. Test thoroughly

---

## 📦 Deliverables

### Required
* **GitHub repository** with clean commit history
* **README.md** with:
  * Setup instructions
  * How to run locally
  * Brief explanation of your approach
  * Any assumptions you made

### Optional
* Live deployment (Vercel, Netlify, etc.)
* Demo video or screenshots

---

## 🎯 What We're Looking For

* **Clean code**: Well-structured, readable, and maintainable
* **User experience**: Intuitive interface with proper feedback
* **Performance**: Efficient data fetching and rendering
* **Responsiveness**: Works well on different screen sizes
* **Error handling**: Graceful handling of edge cases
* **TypeScript usage**: Proper typing throughout

---

## ❓ Questions?

If you run into issues with the API or need clarification on requirements, feel free to reach out. We want you to succeed.

**Note**: If the API endpoint is not accessible, create a mock API or use static JSON data that matches the expected structure.

---

## 📬 Submission

Reply with your GitHub repository link when complete.

Good luck! 🚀
