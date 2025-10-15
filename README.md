# 🛍️ Medusa E-commerce Backend

A powerful e-commerce backend built with Medusa.js and Supabase PostgreSQL database.

## 🚀 Features

- **Full E-commerce API**: Products, Orders, Customers, Carts, Regions
- **Multi-region Support**: Multiple currencies and shipping zones
- **Payment Integration**: Ready for Stripe, PayPal, and other providers
- **Inventory Management**: Stock tracking and reservations
- **Order Management**: Complete order lifecycle
- **Admin Dashboard**: Built-in admin interface
- **RESTful API**: Complete REST API with GraphQL support

## 🏗️ Architecture

- **Framework**: Medusa.js v2
- **Database**: Supabase PostgreSQL
- **Authentication**: JWT-based
- **API**: REST + GraphQL
- **Real-time**: WebSocket support

## 🛠️ Getting Started

### Prerequisites

- Node.js 18+
- PostgreSQL database (Supabase)
- npm or yarn

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/harisharnamm/Ecommerce-Backend.git
   cd Ecommerce-Backend
   ```

2. **Install dependencies**:
   ```bash
   npm install
   ```

3. **Set up environment variables**:
   ```bash
   cp .env.example .env
   ```
   
   Update `.env` with your configuration:
   ```env
   DATABASE_URL=postgresql://username:password@host:port/database
   JWT_SECRET=your-jwt-secret
   COOKIE_SECRET=your-cookie-secret
   MEDUSA_ADMIN_ONBOARDING_TYPE=default
   ```

4. **Run database migrations**:
   ```bash
   npm run build
   npx medusa db:migrate
   ```

5. **Seed the database** (optional):
   ```bash
   npx medusa exec ./src/scripts/seed.ts
   ```

6. **Start the development server**:
   ```bash
   npm run dev
   ```

## 📊 API Endpoints

### Store API (Public)
- `GET /store/products` - List products
- `GET /store/products/:id` - Get product details
- `GET /store/regions` - List regions
- `GET /store/collections` - List collections
- `POST /store/carts` - Create cart
- `GET /store/carts/:id` - Get cart
- `POST /store/carts/:id/line-items` - Add item to cart
- `POST /store/orders` - Create order

### Admin API (Protected)
- `GET /admin/products` - List products (admin)
- `POST /admin/products` - Create product
- `PUT /admin/products/:id` - Update product
- `DELETE /admin/products/:id` - Delete product
- `GET /admin/orders` - List orders
- `PUT /admin/orders/:id` - Update order

## 🔧 Configuration

### Environment Variables

```env
# Database
DATABASE_URL=postgresql://username:password@host:port/database

# Security
JWT_SECRET=your-jwt-secret
COOKIE_SECRET=your-cookie-secret

# Server
PORT=9000
NODE_ENV=development

# Medusa
MEDUSA_ADMIN_ONBOARDING_TYPE=default
```

### Database Schema

The backend uses a comprehensive e-commerce schema including:

- **Products**: Product catalog with variants and options
- **Orders**: Order management and tracking
- **Customers**: Customer management and addresses
- **Carts**: Shopping cart functionality
- **Regions**: Multi-region support
- **Payments**: Payment processing
- **Shipping**: Shipping methods and rates

## 🚀 Deployment

### Railway

1. **Connect your GitHub repository** to Railway
2. **Set environment variables** in Railway dashboard
3. **Deploy automatically** on push to main branch

### Render

1. **Connect your GitHub repository** to Render
2. **Set environment variables** in Render dashboard
3. **Deploy automatically** on push to main branch

### Manual Deployment

1. **Build the application**:
   ```bash
   npm run build
   ```

2. **Start the production server**:
   ```bash
   npm start
   ```

## 📚 API Documentation

### Authentication

Most admin endpoints require authentication:

```bash
curl -H "Authorization: Bearer your-jwt-token" \
     http://localhost:9000/admin/products
```

### Store API Examples

**Get all products**:
```bash
curl http://localhost:9000/store/products
```

**Create a cart**:
```bash
curl -X POST http://localhost:9000/store/carts \
     -H "Content-Type: application/json" \
     -d '{"region_id": "reg_123"}'
```

**Add item to cart**:
```bash
curl -X POST http://localhost:9000/store/carts/cart_123/line-items \
     -H "Content-Type: application/json" \
     -d '{"variant_id": "variant_123", "quantity": 1}'
```

## 🧪 Testing

```bash
# Run tests
npm test

# Run tests with coverage
npm run test:coverage

# Run integration tests
npm run test:integration
```

## 🔒 Security

- JWT-based authentication
- CORS configuration
- Input validation and sanitization
- SQL injection protection
- Rate limiting

## 📈 Performance

- Database indexing for optimal queries
- Caching for frequently accessed data
- Connection pooling
- Query optimization

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📄 License

This project is licensed under the MIT License.

## 🆘 Support

- **Documentation**: [Medusa.js Docs](https://docs.medusajs.com/)
- **Issues**: Create an issue in this repository
- **Community**: Join the Medusa Discord

---

**Built with ❤️ using Medusa.js**