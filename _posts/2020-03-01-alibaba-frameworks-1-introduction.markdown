---
layout: post
title: Ant Design Pro(1) Introduction to the Alibaba Frontend Framworks
date: 2020-03-01 11:23
post-link: https://pro.ant.design/
---

I am going to write a series of posts on the three main contributions of Alibaba to the world of js frameworks.  For anyone who doesn't know, Alibaba is perhaps the most successful tech company in China. Anyone who has used Chinese apps like Alipay or Taobao knows, however, that these apps are essentially huge ecosystems of smaller apps, all of which share a very similar look. This is because, among other things, they were developed using these frameworks, which allow for very fast development of enterprise-grade, frontend-heavy apps.

I personally think these frameworks are fantastic, and they are very popular in China, commonly taught in bootcamps alongside the likes of React and Angular. However there aren't that many tutorials in English, and the documentation for `dva` is mostly only available in Chinese. This motivated me to write a few posts explaining how to work with these tools. Fortunately, they are easy to learn and explain.

On a very high level, all of these tools seek to mitigate or eliminate some of the pain points when working with React.
- `dva` (pronounced 'diva') wraps around `redux`, `redux sagas`, `fetch` and `react router`. `dva` generates a bunch of boilerplate code for you, e.g. pages are automatically generated. To link pages, one simply modifies a config file. Reducers and models are also just added to a config file. It even generates mock data! This reduces typing substantially and improves productivity. What is `dva` good for? It is great for developing those micro frontends within the micro frontends paradigm. One would not develop a large frontend monolith with it because it imposes a layered architecture. But if the architecture is feature-oriented / vertically split then `dva` is quite a good choice for many use cases
- `umi` builds on the `dva` architecture & folder structure to further generate code. The main use `umi` has is in combination with Ant Design Pro where it can generate an entire dashboard at the click of a button. It even generates menus automatically. The workflow with Ant Design Pro is to pull components / blocks/ templates from the library and then modify them, as opposed to writing things from scratch. The library is fairly vast, but if something is no there one can always grab something from elsewhere in the ecosystem or roll your own.
- `antd` (Ant Design) is just a component library similar to Bootstrap, Bulma, Styled Components etc.
- Ant Design Pro wraps all of the tools into a big frontend development tool where one can grab entire ready made templates with all the routing, components, etc. and just modify. 
