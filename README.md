# School Management System

A comprehensive PHP-based School Management System built with Laravel 12, featuring role-based access control for Administrators, Teachers, and Parents, with integrated finance and payment modules.

## Features

### Administrator Portal
- **User Management**: Manage students, teachers, parents, and admin accounts
- **Role & Permissions**: Set and manage user roles
- **Student Profiles**: Comprehensive student information management
- **Staff Management**: Teacher and staff profile oversight
- **Financial Dashboard**: 
  - Track tuition fees and payments
  - Manage invoices and fee structures
  - Monitor outstanding balances
  - Generate financial reports
- **Audit Logs**: Complete system activity tracking
- **Announcements**: Create and manage school-wide announcements

### Teacher Portal
- **Grade Management**: Record and manage student grades and assessments
- **Attendance Tracking**: Mark and view student attendance
- **Class Rosters**: Manage class schedules and student lists
- **Student Profiles**: Access academic and discipline records
- **Financial Clearance**: View student payment status (Yes/No flag)
- **Messaging**: Communicate with parents and administrators

### Parent Portal
- **Child Records**: Secure access to children's academic information
- **Attendance Logs**: View attendance history
- **Grades & Assessments**: Access academic performance data
- **Finance Dashboard**:
  - View outstanding balances
  - Access payment history
  - Download receipts
- **Online Payments**: Make secure payments (integration ready)
- **Messaging**: Communicate with teachers and administrators
- **Announcements**: Receive school updates and notifications

## Technology Stack

- **Framework**: Laravel 12
- **PHP Version**: 8.2+
- **Database**: SQLite (default) - configurable for MySQL/PostgreSQL
- **Frontend**: Tailwind CSS 4.0
- **Build Tool**: Vite
- **Additional**: Vue 3, Inertia.js (optional)

## Installation

### Prerequisites
- PHP 8.2 or higher
- Composer
- Node.js & NPM

### Setup Steps

1. **Clone or navigate to the project directory**
   ```bash
   cd "c:\Users\caiap\Videos\School management system\schoolms"
   ```

2. **Install PHP dependencies**
   ```bash
   composer install
   ```

3. **Install Node dependencies**
   ```bash
   npm install
   ```

4. **Configure environment**
   ```bash
   copy .env.example .env
   php artisan key:generate
   ```

5. **Create database file** (for SQLite)
   ```bash
   type nul > database\database.sqlite
   ```

6. **Run migrations**
   ```bash
   php artisan migrate
   ```

7. **Seed the database**
   ```bash
   php artisan db:seed
   ```

8. **Build assets**
   ```bash
   npm run build
   ```

9. **Start the development server**
   ```bash
   php artisan serve
   ```

Visit `http://localhost:8000` in your browser.

## Default Login Credentials

### Administrator
- Email: `admin@school.com`
- Password: `password`

### Teacher
- Email: `teacher@school.com`
- Password: `password`

### Parent
- Email: `parent@school.com`
- Password: `password`

## Database Schema

### Core Tables
- `users` - System users (admins, teachers, parents)
- `roles` - User roles definition
- `user_roles` - Role assignments
- `students` - Student profiles and information

### Finance Tables
- `fee_structures` - Fee definitions and amounts
- `invoices` - Student invoices
- `invoice_items` - Invoice line items
- `payments` - Payment records and transactions

### Academic Tables
- `grades` - Student grades and assessments
- `attendance` - Attendance records
- `class_rosters` - Class and schedule management

### Communication Tables
- `messages` - Internal messaging system
- `announcements` - School-wide announcements

### System Tables
- `audit_logs` - System activity tracking

## Security Features

- Role-based access control (RBAC)
- Session management
- CSRF protection
- Password hashing (bcrypt)
- SQL injection prevention (Eloquent ORM)
- XSS protection
- Activity logging and audit trails

## Payment Integration

The system is designed to integrate with payment gateways. Current implementation includes:
- Payment recording and tracking
- Invoice generation
- Receipt generation
- Balance management
- Payment status tracking

To integrate with a payment gateway:
1. Install the gateway SDK via Composer
2. Update `FinanceController::processPayment()` method
3. Configure gateway credentials in `.env`
4. Implement webhook handlers for payment confirmations

## Testing

Run the test suite:
```bash
php artisan test
```

## Development

### Running in development mode
```bash
# Terminal 1: Start Laravel server
php artisan serve

# Terminal 2: Start Vite dev server
npm run dev
```

### Code Style
The project follows PSR-12 coding standards. Format code using:
```bash
vendor/bin/pint
```

## Project Structure

```
app/
├── Http/
│   ├── Controllers/
│   │   ├── Admin/          # Administrator controllers
│   │   ├── Teacher/        # Teacher controllers
│   │   ├── Parent/         # Parent controllers
│   │   └── Auth/           # Authentication controllers
│   └── Middleware/
│       ├── CheckRole.php   # Role-based access control
│       └── LogActivity.php # Activity logging
├── Models/                 # Eloquent models
database/
├── migrations/             # Database migrations
└── seeders/               # Database seeders
resources/
├── views/                 # Blade templates
├── css/                   # Stylesheets
└── js/                    # JavaScript files
routes/
└── web.php               # Application routes
```

## Benefits

### For Administrators
- Complete control over user management
- Real-time financial tracking
- Comprehensive reporting capabilities
- Audit trail for compliance
- Centralized communication

### For Teachers
- Efficient grade entry and management
- Quick attendance marking
- Student performance tracking
- Easy parent communication
- Financial clearance verification

### For Parents
- Transparent access to child's records
- Real-time grade and attendance updates
- Convenient online payments
- Receipt downloads
- Direct teacher communication

## Support

For issues, questions, or contributions:
1. Check existing documentation
2. Review audit logs for system issues
3. Contact system administrator

## License

The Laravel framework is open-sourced software licensed under the MIT license.

## Acknowledgments

Built with Laravel 12, leveraging the robust PHP ecosystem for educational institution management.

