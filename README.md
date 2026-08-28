# Loom Edu

Loom Edu is a scholarship discovery and application platform.

## Stack
- React + Vite
- Supabase Auth + PostgreSQL
- Vercel deployment

## Required environment variables
`VITE_SUPABASE_URL` and `VITE_SUPABASE_PUBLISHABLE_KEY`.

## Admin dashboard
The admin dashboard is available at `/admin`. Access is protected by the `profiles.role` column and Supabase RLS policies.

After registering your own account, make that account an administrator in the Supabase SQL Editor:

```sql
update public.profiles
set role = 'admin'
where id = (select id from auth.users where email = 'YOUR_EMAIL');
```

Then sign out and back in. The **Admin** link will appear in the navigation.

Admins can:
- Create, edit, feature, and delete scholarships
- View applicants and their profile names/countries
- Change application status

The database schema, RLS policies, admin role support, and starter scholarship records are provisioned in the connected Supabase project.