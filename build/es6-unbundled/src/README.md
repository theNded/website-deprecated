## Jump Logic:

This part is for tab visualization
1. `site-data-provider` provides `{{category}}` (title, name included)
2. `_categoryChanged` triggered
  - `change-section` event sent to site-app
3. `_onChangeSection` triggered
  - `categoryName` changed
  - site-tabs selected=[[categoryName]] changed
  - `IronSelectableBehavior` triggered (mixinBehavior, Polymer inner implementation)

This part is for content rendering
1. app-location gets `{{route}}`
2. app-route analyzes `{{route}}`, get `{{routeData.page}}` and `{{subroute}}`
3. `_routeChanged` triggered
  - analyze `page` and `routeData.page` to decide `page` in 4 major categories
  - analyze `subroute` to decide `page` in details
4. `_pageChanged` triggered
  - lazy import html
5. (perhaps) force html rendering in shadow element