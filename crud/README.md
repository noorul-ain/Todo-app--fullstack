# Todo App - Full Stack CRUD Application

A complete full-stack CRUD application built with Next.js 15, MongoDB, Mongoose, and Tailwind CSS.

## Features

- ✅ **Create**: Add new items with title and description
- ✅ **Read**: Display all items with creation dates
- ✅ **Update**: Edit existing items inline
- ✅ **Delete**: Remove items with confirmation
- 🔄 **Real-time**: Instant UI updates after operations
- 📱 **Responsive**: Mobile-friendly design with Tailwind CSS
- ⚡ **Fast**: Built with Next.js 15 and optimized for performance

## Tech Stack

- **Frontend**: Next.js 15, React 19, TypeScript
- **Styling**: Tailwind CSS 4
- **Backend**: Next.js API Routes
- **Database**: MongoDB with Mongoose ODM
- **State Management**: React Hooks (useState, useEffect)

## Prerequisites

- Node.js 18+ 
- MongoDB running locally or MongoDB Atlas account
- npm or yarn package manager

## Setup Instructions

### 1. Install Dependencies

```bash
npm install
```

### 2. Environment Configuration

Create a `.env.local` file in the root directory:

```bash
MONGODB_URI=mongodb://localhost:27017/todo-app
```

**For MongoDB Atlas users:**
```bash
MONGODB_URI=mongodb+srv://<username>:<password>@<cluster>.mongodb.net/todo-app?retryWrites=true&w=majority
```

### 3. Start MongoDB

**Local MongoDB:**
```bash
# Start MongoDB service
mongod

# Or using Docker
docker run -d -p 27017:27017 --name mongodb mongo:latest
```

**MongoDB Atlas:**
- Create a free cluster at [MongoDB Atlas](https://www.mongodb.com/atlas)
- Get your connection string and add it to `.env.local`

### 4. Run the Application

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## Project Structure

```
src/
├── app/
│   ├── api/
│   │   └── items/
│   │       ├── route.ts          # GET, POST /api/items
│   │       └── [id]/
│   │           └── route.ts      # GET, PUT, DELETE /api/items/[id]
│   ├── globals.css               # Tailwind CSS styles
│   ├── layout.tsx                # Root layout
│   └── page.tsx                  # Main CRUD interface
├── lib/
│   └── mongodb.ts                # MongoDB connection utility
└── models/
    └── Item.ts                   # Mongoose Item model
```

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/api/items` | Fetch all items |
| `POST` | `/api/items` | Create new item |
| `GET` | `/api/items/[id]` | Fetch single item |
| `PUT` | `/api/items/[id]` | Update item |
| `DELETE` | `/api/items/[id]` | Delete item |

## Data Model

```typescript
interface Item {
  _id: string;
  title: string;        // Required, max 100 chars
  description: string;  // Required, max 500 chars
  createdAt: Date;      // Auto-generated timestamp
}
```

## Usage

1. **Add Item**: Fill out the form at the top and click "Add Item"
2. **View Items**: All items are displayed below with creation dates
3. **Edit Item**: Click the "Edit" button to modify title/description inline
4. **Delete Item**: Click "Delete" and confirm to remove an item
5. **Real-time Updates**: UI automatically refreshes after each operation

## Features

- **Form Validation**: Required fields with error messages
- **Loading States**: Visual feedback during API calls
- **Success/Error Messages**: Toast notifications for all operations
- **Responsive Design**: Works on desktop, tablet, and mobile
- **Inline Editing**: Edit items without page navigation
- **Confirmation Dialogs**: Prevent accidental deletions
- **Auto-refresh**: Items list updates automatically

## Development

```bash
# Development server
npm run dev

# Build for production
npm run build

# Start production server
npm start

# Lint code
npm run lint
```

## Troubleshooting

**MongoDB Connection Issues:**
- Ensure MongoDB is running on the specified port
- Check your connection string in `.env.local`
- Verify network access for Atlas connections

**Build Errors:**
- Clear `.next` folder: `rm -rf .next`
- Reinstall dependencies: `rm -rf node_modules && npm install`

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

MIT License - feel free to use this project for learning and development!
