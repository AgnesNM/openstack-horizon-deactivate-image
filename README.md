# OpenStack Horizon: Deactivate/Reactivate Image Feature

A feature contribution to [OpenStack Horizon](https://github.com/openstack/horizon), the web-based dashboard for OpenStack. Adds the ability to deactivate and reactivate images from the Horizon dashboard.

## What this does

When you deactivate an image, its status changes and its data can no longer be used. You can later reactivate it, restoring it to Active status. The feature appears as a dropdown option next to the Launch button on the Horizon images dashboard.

## Original contribution

Submitted, reviewed, and merged via OpenDev Gerrit:  
https://review.opendev.org/c/openstack/horizon/+/926379

## Related writing

I documented the full process of building this feature:  
*"[From Concept to Code: Building the Deactivate/Reactivate Feature in OpenStack Horizon](https://superuser.openinfra.org/articles/from-concept-to-code-building-the-deactivate-reactivate-feature-in-openstack-horizon/)"*  
Published on Superuser (OpenInfra Foundation), December 2024

## Files changed

### Backend (Python/Django)
- `openstack_dashboard/api/glance.py` — API calls to the Glance image service
- `openstack_dashboard/api/rest/glance.py` — REST API endpoints for the dashboard

### Frontend (AngularJS)
- `openstack_dashboard/static/app/core/images/actions/actions.module.js` — Registers the new actions
- `openstack_dashboard/static/app/core/images/actions/deactivate-image.service.js` — Deactivate service
- `openstack_dashboard/static/app/core/images/actions/reactivate-image.service.js` — Reactivate service
- `openstack_dashboard/static/app/core/images/actions/edit.action.service.js` — Edit action service
- `openstack_dashboard/static/app/core/images/steps/deactivate/deactivate.html` — Modal template
- `openstack_dashboard/static/app/core/images/steps/deactivate/deactivate.controller.js` — Modal controller
- `openstack_dashboard/static/app/core/openstack-service-api/glance.service.js` — Glance API service

### Config
- `openstack_dashboard/karma.conf.js` — Test configuration
