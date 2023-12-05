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

# Setting Up Drizzle ORM

> Package.json Get Scripts - https://github.com/webprodigies/webprodigies-cypress/blob/main/package.json
> Tsconfig.json - "es6" in target

npm run generate (create 0000_ in migrations/)
npm run push (push to supbabase)
npm run dev

> Supabase - Table Editor - Workspaces

