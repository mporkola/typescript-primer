# Typescript at Wolt - learnings

---

## Scope

This isn't basics of Typescript, you find plenty of those online

---

## Domain types

Working with e.g. our beloved menu data model? You should create a `types.ts` file for that, which contains all the types specific to that domain. If you're using module structure in your codebase, you should of course place the file in the relevant module directory. This way you'll have a good overview of the data you're working with, and you don't need to wonder where the typings should reside.

---
```typescript
export interface MenuLanguage {
  language: Locale;
  autotranslated: boolean;
  name: string;
  primary: boolean;
}

export interface Menu {
  languages: Array<MenuLanguage>;
  language: Locale;
  id: mongoId;
  categories: Array<Category>;
  items: Array<Item>;
  options: Array<unknown>;
  specials: Array<SpecialWithInlineOptionInstance>;
}
```
@[2](Globally defined woltwide data types)
@[1, 9](Hierarchic system of domain data types)
@[14](`unknown` keeps you safe from making assumptions about objects you shouldn't care about)

---

## Go strict

---

## Use eslint with all the plugins

---

##