#  St-Laurent-le-minier website
# WORKLOAD OVERVIEW

## Design
### Overall design
- Typography
- Colors
- Page layouts (mobile / tablet / laptop)
### Individual pages
- Home page
- Default presentation pages
- Agenda & Subscription pages (e.g. Salle Roger Dellene, Cantine/guarderie etc.)
- Events pages 
- Blog pages (where news, announcements etc. can be posted)
- Contact page
- Newsletter: default email templates
- Header / Footer
## Development
### HTML / CSS / templates
- The designs above need to be "reproduced" on the browser (for all screen sizes)
- Navigation menu(s)
### User management (mostly out-of-the-box, slight customizations):
- User management system 
- User roles / permissions i.e. admins, authors, volunteers (mostly out-of-the-box, slight customizations)
- GDPR compliance ( users must be able to view / download / delete any of their own data  we keep )
### CMS customization (mostly out-of-the-box, slight customizations):
- Custom toolbar buttons and plugins for (even) easier content creation
- Unit tests
### Email back-end (for emails sent programmatically)
- Integration with an email delivery app (e.g. mailgun, sendinblue, sendgrid etc.) This ensures emails are not blocked nor end up in the spam folder.
- Unit tests
### SEO optimization
- Template work
- django-page-meta configuration
### Cookie-consent-management (mostly out-of-the-box, slight customizations)
- django-cookie-consent integration
### Blog application (mostly out-of-the-box, slight customizations)
- Configuration
- Templates customization / styles to match design
### Newsletter
- Maintain subscribers' mailing list(s)
- 2-way synch with external API for mail-delivery / marketing service
- Asynchronous task (span big campaigns over several days not to exceed 300 emails per day limit)
- Unit tests
### Events
- Event model
- Calendar
- Unit tests
### Agenda / subscriptions
- Booking
- Confirmation 
- Custom permissions
- email confirmation
- Scheduling / recurrent events 
- Calendar

### Alerte meteo
- meteofrance-api integration (https://pypi.org/project/meteofrance-api/)
- CMS Plugin
- Unit tests

### Submissions app
- Submission model (ideas/proposals or ads)
- CMS PLugin
- email confirmation
- Unit tests

## Infrastructure
- Server hosting
- DNS changes ("transfer" domain name to new site)
- email solution (setting up @saint-laurent-le-minier.fr mailboxes)
    - setup required accounts
- schedule database backups

## Collaboration
### Meetings
- Precise design specs
- Validate content
- Precise extra functionalities
- Feedback iterations
### Training
- CMS usage for admins
- CMS usage for editors
- Blog post creation
- Search Engine Optimization
- Newsletter / Campaigns
- Custom apps
## Support
- Software updates
- Inrastructure monitoring

## Technical details
For the tech savvy here is a list of the proposed stack:

**Docker** is used for containerizing the application (https://www.docker.com/)
### Services
- Back-end:
    - language: python (https://www.python.org/)
    - framework: django (https://www.djangoproject.com/)
    - Content Management System: djangoCMS (https://www.django-cms.org/en/)
- Database: Postgresql (https://www.postgresql.org/)
- Caching / message broker: Redis (https://redis.io/)
- Task queue / scheduler: Celery (https://docs.celeryproject.org/en/stable/)
- Search engine: elastisearch (https://www.elastic.co/elastic-stack)
### Devops
- Version control: git (https://git-scm.com/)
- Duplicated staging and live server environments
- Automated pipelines for testing & continuous deployment
- Automated software updates via dependabot (https://dependabot.com/)
- log monitoring via sentry (https://sentry.io)
