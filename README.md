# dynamic-display-backend
Backend repo for DIY dynamic displays

## Vision
- Simple
- Flexible
- Realistic to our use cases

### References
- [Vestaboard dev docs](https://docs.vestaboard.com/docs/local-api/introduction/?_gl=1*tzsb1s*_gcl_au*MjA0NDc4OTkwLjE3NDAyNDYwNjM.*_ga*NTkzMjIyNTI1LjE3NDAyNDYwNjM.*_ga_JE1QENZVTH*MTc0MTE0NDAyNi4xMC4xLjE3NDExNDQ0OTUuMjcuMC43MDQ5NjM5MjQ.&_ga=2.32622909.284988025.1741060193-593222525.1740246063)

### Tech stack
- OPTION A:
  - NextJS (for backend server)
    - [Task scheduling](https://docs.nestjs.com/techniques/task-scheduling)
    - [Dynamic API](https://docs.nestjs.com/techniques/task-scheduling#dynamic-timeouts)
  - [DB TBD](https://nextjstemplates.com/blog/best-database-for-nextjs)
- OPTION B:
  - Django (for backend server)
    - Celery Beat (for async job scheduling)
  - SQLite (for simple DB)
  - Celery (for async workers)
  - Redis (for async job broker)
- Vestaboard Frontend repo: [vestaboard-plus-plus](https://github.com/NahItsFine/vestaboard-plus-plus)

### Features
- settings
  - quiet hours
- sync channels
  - push - message (reflect current state, option to clear, button to push)
  - mode - spotify (ON/OFF)
- async channels (ON/OFF, recurrence rule via cron)
  - news
  - sports
  - calendar
  - quote of the day
  - random facts
  - stocks
  - NOTE: save these async channels in DB so app can reschedule them on startup
- supports multiple types of displays

## Nerd stuff
- git branch convention: `<initials>/<branch name>`
- git commit convention: `<feat/fix/chore>: <description>`
- dev flow (* denotes if no feature branch): 
  - `git checkout -b tn/update-readme`
  - *do stuff
  - *`git add . && git commit -m "chore: update readme"`
  - `git checkout main && git pull origin main`
  - `git merge tn/update-readme`
  - *`git push origin main`