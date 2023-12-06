# Setup and installing Packages

npx create-next-app@latest .

√ Would you like to use TypeScript? Yes
√ Would you like to use ESLint? Yes
√ Would you like to use Tailwind CSS? Yes
√ Would you like to use `src/` directory? Yes
√ Would you like to use App Router? (recommended) Yes
√ Would you like to customize the default import alias (@/*)? No 

> Drizzle

npm i drizzle-orm postgres dotenv
npm i drizzle-kit prettier -D

create .env & add to .gitignore

# Supabase Datase Setup

https://supabase.com/ - login - new project - webprodigies-cypress
- copy database password to .env PW - create new project - 
>.env

DATABASE_URL=(Connection string + pw)
NEXT_PUBLIC_SUPABASE_URL=(URL)
NEXT_PUBLIC_SUPABASE_ANON_KEY=(anon_key)
SERVICE_ROLE_KEY=(service_role
PW=(password)

# Setting Up Drizzle ORM (subabase + workspaces table)

> Package.json Get Scripts - https://github.com/webprodigies/webprodigies-cypress/blob/main/package.json
> Tsconfig.json - "es6" in target

npm run generate (create 0000_ in migrations/)
npm run push (push to supbabase)
npm run dev

> Supabase - Table Editor - Workspaces


# Setting Up Drizzle ORM (folders  & files tables)

> files, folders i schema.ts

npm run generate & npm run push

> Supabase - SQL Editor - Quickstarts - Stripe Subscriptions - Edit ...
"""
  -- Stores your customer's payment instruments.
  updated_at timestamp with time zone,
  payment_method jsonb,
  email text
);
"""

"""
alter table users
  enable row level security;
create policy "Everyone can view user data." on users
  for select using (true);
create policy "Can update own user data." on users
  for update using (auth.uid() = id);
"""

"""
$$
  begin
    insert into public.users (id, full_name, avatar_url, email)
    values (new.id, new.raw_user_meta_data->>'full_name', new.raw_user_meta_data->>'avatar_url', new.email);
    return new;
  end;
$$
"""

> Run (success) - Table Editor 

npm run pull (get external changes)

> migrations/schema.ts - change
import { sql } from 'drizzle-orm'
"default(timezone('utc'::text, now()))" to "default(sql`now()`)"

## Fix: Spelling Error
"fix spell error in supbase/schema.ts"
npm run generate
npm run push 
npm run pull
"migrations/schema.ts" is updated

# Setting Up Drizzle ORM (layout)

...

# Shadcn UI Library for NextJS 13

npx shadcn-ui@latest init

√ Would you like to use TypeScript (recommended)? yes
√ Which style would you like to use? » Default
√ Which color would you like to use as base color? » Slate
√ Where is your global CSS file? src/app/globals.css
√ Would you like to use CSS variables for colors? yes
√ Where is your tailwind.config.js located? tailwind.config.js
√ Configure the import alias for components: @/components
√ Configure the import alias for utils: @/lib/utils
√ Are you using React Server Components? yes
√ Write configuration to components.json. Proceed? yes

# How to import Figma colors into our app - Optional
## (We're using shadcn theme colors. But here's how to do it!)

> Goto Figma Design - UI System - "Plugins: Figma Tailwindcss" -
> "Next" - "Pick base font-size: 16px" - "Next" - "Next" - 
> add dark mode light mode > "tailwind.config.js" -> add after card

# Light and Dark mode setup

> shadcn website - "https://ui.shadcn.com/docs/dark-mode/next"

npm install next-themes

> "https://ui.shadcn.com/themes" - "Customize" - "Violet, 0.5, Dark" - "Copy Code"
> replace "globals.css" 

# Landing Page: add first sections + title section

npx shadcn-ui@latest add button
npx shadcn-ui@latest add dropdown-menu

# Landing Page: add testimonial section

npx shadcn-ui@latest add avatar
npx shadcn-ui@latest add card

# Landing Page: add pricing plan

...

# Login & Signup Authentication With Supabase

> https://supabase.com/docs/guides/auth/auth-helpers/nextjs

npm install @supabase/auth-helpers-nextjs @supabase/supabase-js

npx shadcn-ui@latest add form
npx shadcn-ui@latest add input
