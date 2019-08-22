# Project structure

Project has been divided into 4 layers `dataaccess`, `services`, `core`, `view`.
Generally lower layer should not access components from upper layers.
```
src
  ├── app
  │   ├── core
  │   │   ├── component1
  │   │   │   ├── state.ts // state types, initial models, basic model operations
  │   │   │   ├── sagas.ts // sagas related to component
  │   │   │   ├── sagas.spec.ts // tests for sagas.ts
  │   │   │   ├── reducers.ts // reducer for components
  │   │   │   └── actions.ts // actions
  │   │   ├── state.ts // global state
  │   │   ├── sagas.ts // wrapper for all sagas
  │   │   └── reducers.ts // wrapper for all reducers
  │   ├── dataaccess // contains rest calls, all related to data calls
  │   ├── services // higher level of accessing data, can relate to more data access calls, other services
  │   ├── views
  │   │   ├── page1
  │   │   │    ├── item.tsx
  │   │   │    └── page1.tsx
  │   │   ├── page2.tsx
  │   │   └── page2.tsx
  │   └── index.tsx
  ├── components // reusable visual components, not related to any dialog in any app
  ├── styles // reusable styles, if sass still used
  │   └── index.scss
  └── helpers // reusable helpers in whole app
```