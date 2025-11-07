# GitHub Push Checklist for Laravel Blog Project

## Pre-Push Verification Steps

### 1. Git Configuration Check
- [ ] Verify git is initialized: `git status`
- [ ] Check remote repository is configured: `git remote -v`
- [ ] Ensure remote URL is correct: `https://github.com/haa464/laravel-blog-learn.git`
- [ ] Verify current branch name: `git branch`

### 2. File Status Check
- [ ] Check for uncommitted changes: `git status`
- [ ] Verify all important files are tracked: `git ls-files`
- [ ] Ensure no sensitive files are committed (.env, auth.json, etc.)
- [ ] Verify .gitignore is properly configured

### 3. Files to Verify Are Tracked
- [ ] `composer.json` and `composer.lock`
- [ ] `package.json`
- [ ] `README.md`
- [ ] `.gitignore` and `.gitattributes`
- [ ] `artisan`
- [ ] `phpunit.xml`
- [ ] `vite.config.js`
- [ ] `app/` directory (Controllers, Models, Providers)
- [ ] `bootstrap/app.php` and `bootstrap/providers.php`
- [ ] `config/` directory (all config files)
- [ ] `database/` directory (migrations, factories, seeders)
- [ ] `public/` directory (index.php, favicon.ico, robots.txt)
- [ ] `resources/` directory (css, js, views)
- [ ] `routes/` directory (web.php, console.php)
- [ ] `tests/` directory (Feature, Unit tests)

### 4. Files That Should Be Ignored (via .gitignore)
- [ ] `vendor/` directory (should NOT be committed)
- [ ] `node_modules/` directory (should NOT be committed)
- [ ] `.env` file (should NOT be committed)
- [ ] `database/database.sqlite` (should NOT be committed)
- [ ] `storage/logs/` (should NOT be committed)
- [ ] `public/build/` and `public/hot/` (should NOT be committed)

### 5. Commit and Push Steps
- [ ] Stage all changes: `git add -A`
- [ ] Check what will be committed: `git status`
- [ ] Commit changes with descriptive message: `git commit -m "Your commit message"`
- [ ] Pull remote changes if any: `git pull origin main --allow-unrelated-histories`
- [ ] Resolve any merge conflicts if they occur
- [ ] Push to GitHub: `git push origin main`
- [ ] Verify push was successful: Check GitHub repository

### 6. Post-Push Verification
- [ ] Visit GitHub repository: https://github.com/haa464/laravel-blog-learn
- [ ] Verify all folders are visible (app, config, database, resources, routes, tests)
- [ ] Verify all important files are present
- [ ] Check that ignored files are NOT in the repository
- [ ] Verify README.md is properly displayed

## Common Issues and Solutions

### Issue: "Updates were rejected because the tip of your current branch is behind"
**Solution:**
```bash
git pull origin main --allow-unrelated-histories
# Resolve any conflicts
git add .
git commit -m "Merge remote changes"
git push origin main
```

### Issue: Authentication Error
**Solution:**
- Use Personal Access Token instead of password
- Or configure SSH keys for GitHub

### Issue: Merge Conflicts in README.md
**Solution:**
- Keep local version if it's more complete
- Or merge both versions appropriately
- Remove conflict markers (<<<<<<<, =======, >>>>>>>)

## Quick Command Reference

```bash
# Check status
git status

# Add all files
git add -A

# Commit
git commit -m "Your message"

# Check remote
git remote -v

# Pull changes
git pull origin main

# Push changes
git push origin main

# View tracked files
git ls-files

# View commit history
git log --oneline -5
```

## Notes
- Always ensure `.env` file is NOT committed (contains sensitive data)
- `vendor/` and `node_modules/` should be installed via `composer install` and `npm install` after cloning
- Database file (`database.sqlite`) should not be committed
- Storage logs should not be committed

