# Trucking Invoice Management System

A comprehensive trucking invoice and broker management application designed to streamline document processing and maintenance tracking for transportation industry professionals.

## Features

### 📋 Invoice Management
- Create, edit, and manage professional invoices
- Real-time invoice preview with PDF generation
- Color-coded status indicators (Draft, Issued, Paid, Overdue)
- Payment tracking with visual status updates
- Company logo customization with automatic resizing
- Multiple payment terms including 5% quick pay option

### 🚛 Broker Management
- Comprehensive broker database
- Save and reuse broker information
- Track earnings by broker
- Monitor invoice due dates and payment status

### 📄 Document Processing
- Advanced OCR text extraction from PDFs and images
- Document scanner with edge detection (similar to CamScanner)
- Multi-page scanning capabilities
- Real-time OCR confidence scoring
- Automatic data extraction from rate confirmations
- Document management system for rate confirmations and BOLs

### 📊 Financial Tracking
- Mileage tracking system with automatic entries
- Maintenance cost tracking and summaries
- Earnings monitoring by broker
- Payment status visualization
- Dashboard with financial overview

### 🔧 Truck Maintenance
- Truck inventory management
- Maintenance log tracking
- Cost summaries and spending analysis
- Service history records

### 📱 Mobile Support
- Progressive Web App (PWA) capabilities
- Mobile-optimized interface for iOS and Android
- Touch-friendly navigation
- Responsive design for all screen sizes

### 🔐 Security
- User authentication system
- Secure session management
- Password reset functionality
- Protected routes and data access

## Technology Stack

### Backend
- **Node.js** with TypeScript
- **Express.js** web framework
- **PostgreSQL** database with Drizzle ORM
- **Passport.js** for authentication
- **Multer** for file uploads
- **OpenAI API** for intelligent data extraction
- **Tesseract.js** for OCR processing
- **OpenCV.js** for document edge detection

### Frontend
- **React** with TypeScript
- **Vite** for fast development and building
- **TanStack Query** for data fetching and caching
- **Wouter** for routing
- **Tailwind CSS** for styling
- **shadcn/ui** component library
- **Framer Motion** for animations
- **React Hook Form** with Zod validation

### Database
- **PostgreSQL** with connection pooling
- **Drizzle ORM** for type-safe database operations
- **Automated migrations** with schema validation

## Getting Started

### Prerequisites
- Node.js (v18 or higher)
- PostgreSQL database
- OpenAI API key (for document processing)

### Installation

1. **Clone the repository**
   ```bash
   git clone [repository-url]
   cd trucking-invoice-app
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Set up environment variables**
   Create a `.env` file with:
   ```
   DATABASE_URL=your_postgresql_connection_string
   OPENAI_API_KEY=your_openai_api_key
   SESSION_SECRET=your_session_secret
   ```

4. **Initialize database**
   ```bash
   npm run db:push
   ```

5. **Start development server**
   ```bash
   npm run dev
   ```

The application will be available at `http://localhost:5000`

## Usage

### Creating Invoices
1. Navigate to the invoice creation page
2. Fill in company and job details
3. Upload rate confirmation documents for auto-extraction
4. Review and save as draft or issue immediately

### Document Scanning
1. Use the built-in scanner to capture documents
2. Edge detection automatically crops and enhances images
3. OCR extracts text and populates invoice fields
4. Review confidence scores for accuracy verification

### Broker Management
1. Add brokers with complete contact information
2. Track payment history and terms
3. Monitor outstanding invoices and due dates

### Maintenance Tracking
1. Register trucks in the system
2. Log maintenance activities and costs
3. View spending summaries and service history

## API Endpoints

### Authentication
- `POST /api/register` - User registration
- `POST /api/login` - User login
- `POST /api/logout` - User logout
- `GET /api/user` - Get current user

### Invoices
- `GET /api/invoices` - List all invoices
- `POST /api/invoices` - Create new invoice
- `GET /api/invoices/:id` - Get specific invoice
- `PATCH /api/invoices/:id` - Update invoice
- `DELETE /api/invoices/:id` - Delete invoice

### Brokers
- `GET /api/brokers` - List all brokers
- `POST /api/brokers` - Create new broker
- `PATCH /api/brokers/:id` - Update broker

### Documents
- `POST /api/documents` - Upload document
- `GET /api/documents` - List documents
- `GET /api/documents/:id/download` - Download document

### Mileage Tracking
- `GET /api/mileage` - Get mileage entries
- `POST /api/mileage` - Create mileage entry
- `PATCH /api/mileage/:id` - Update mileage entry

## Development

### Project Structure
```
├── client/                 # Frontend React application
│   ├── src/
│   │   ├── components/    # Reusable UI components
│   │   ├── pages/         # Application pages
│   │   ├── hooks/         # Custom React hooks
│   │   └── lib/           # Utility functions
├── server/                # Backend Express application
│   ├── routes.ts          # API route definitions
│   ├── storage.ts         # Database operations
│   ├── auth.ts           # Authentication logic
│   └── ocr.ts            # Document processing
├── shared/               # Shared types and schemas
│   └── schema.ts         # Database schema and validation
└── uploads/              # File upload directory
```

### Key Commands
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run db:push` - Push schema changes to database
- `npm run db:studio` - Open database studio

## Features in Detail

### OCR and Document Processing
The application uses advanced OCR technology to extract data from scanned documents:
- **Tesseract.js** for text recognition
- **OpenCV.js** for image preprocessing and edge detection
- **OpenAI API** for intelligent data extraction and formatting
- Real-time confidence scoring to ensure accuracy

### Invoice Status Management
Visual indicators help track invoice lifecycle:
- **Draft** - Gray indicator for work-in-progress invoices
- **Issued** - Blue indicator for sent invoices
- **Paid** - Green highlighting for completed payments
- **Overdue** - Red indicator for past-due invoices

### Mobile Optimization
The application is fully optimized for mobile devices:
- Touch-friendly interface with larger tap targets
- Responsive layouts that adapt to screen size
- Progressive Web App capabilities for app-like experience
- Offline functionality for basic operations

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## License

This project is licensed under the MIT License.

## Support

For support and questions, please contact the development team or create an issue in the repository.
