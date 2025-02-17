jika ketika di clone tidak jalan mohon pake link yang ini:
github BE : https://github.com/CyanoCream/travel-be
github FE : https://github.com/CyanoCream/travel_fe

# Travel Booking System

This repository contains two projects:

1. Backend API (Laravel 11) - Located in `travel-order` folder
2. Frontend Application (Vue.js) - Located in `fe-travel` folder

## Backend Setup (Laravel)

### Prerequisites

- PHP 8.2 or higher
- Composer
- PostgreSQL
- Copy of `.env.example` to `.env`

### Installation Steps

1. Navigate to Laravel project directory:

```bash
cd travel-order
```

2. Install PHP dependencies:

```bash
composer install
```

3. Configure environment:

```bash
cp .env.example .env
```

4. Configure your PostgreSQL database connection in `.env` file:

```
DB_CONNECTION=pgsql
DB_HOST=127.0.0.1
DB_PORT=5432
DB_DATABASE=your_database_name
DB_USERNAME=your_username
DB_PASSWORD=your_password
```

5. Generate application key:

```bash
php artisan key:generate
```

6. Run database migrations:

```bash
php artisan migrate
```

7. Run database seeders in the following order:

```bash
php artisan db:seed --class=UserSeeder
php artisan db:seed --class=TravelScheduleSeeder
php artisan db:seed --class=TicketBookingSeeder
```

8. Start the Laravel development server:

```bash
php artisan serve
```

The API will be available at `http://localhost:8000`

## Frontend Setup (Vue.js)

### Prerequisites

- Node.js (Latest LTS version recommended)
- npm or yarn

### Installation Steps

1. Navigate to Vue.js project directory:

```bash
cd fe-travel
```

2. Install dependencies:

```bash
npm install
# or
yarn install
```

3. Configure the API endpoint in your environment file if necessary

4. Start the development server:

```bash
npm run dev
# or
yarn dev
```

The frontend application will be available at `http://localhost:5173` (or the port shown in your terminal)

## Default User Accounts

After running the seeders, the following user accounts will be available:

### Admin Account

- Email: admin@example.com
- Password: password123
- Role: ADMIN

### Passenger Accounts

All passenger accounts use the same password: password123

- john@example.com
- jane@example.com
- bob@example.com
- alice@example.com
- charlie@example.com

## Application Features

### Admin Dashboard

After logging in as admin, you can:

1. Access the admin dashboard with passenger reports
2. Manage Travel Schedules:
   - Click "Manage Schedules" button
   - Add new destinations and schedules
   - View passenger booking reports for each travel schedule
3. View comprehensive reports including total passengers per travel schedule

### Passenger Features

After logging in as a passenger, you can:

1. Book Trips:

   - View available travel schedules in the "Book Trip" menu
   - Click "Booking" to reserve a ticket
   - Receive success/failure notifications
   - Auto-redirect to dashboard upon successful booking

2. Manage Bookings (My Booking menu):
   - View all bookings and their status
   - Make payments using "Pay Now" button
   - Submit payment proof via link
   - Download invoice (available after booking is confirmed)
   - Cancel bookings
   - Access confirmed booking invoices from the dashboard

## Additional Notes

- Make sure both backend and frontend servers are running simultaneously
- Check the console for any error messages during setup
- Ensure PostgreSQL service is running before starting the backend server
- Backend API documentation can be found at `/api/documentation` (if implemented)

## Troubleshooting

If you encounter any issues:

1. Ensure all prerequisites are installed and up to date
2. Check if PostgreSQL service is running
3. Verify database credentials in `.env` file
4. Clear Laravel cache:

```bash
php artisan config:clear
php artisan cache:clear
```

5. For frontend issues, try removing `node_modules` and reinstalling dependencies
