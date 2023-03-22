---
# Leave the homepage title empty to use the site title
title:
date: 2022-10-24
type: landing

sections:
  - block: about.avatar
    id: about
    content:
      # Choose a user profile to display (a folder name within `content/authors/`)
      username: admin
      # Override your bio text from `authors/admin/_index.md`?
      text:
  - block: collection
    content:
      title: Recent Publications
        folders:
          - publication
        exclude_featured: true
    design:
      columns: '2'
      view: citation
  - block: contact
    id: contact
    content:
      title: Contact
      # Contact (add or remove contact options as necessary)
      email: o.robinson@ucl.ac.uk
      phone:  +44 20 7679 1150
      address:
        street: Alexandra House, 17-19 Queen Square
        city: London
        postcode: 'WC1N 3AZ'
        country: United Kingdom
        country_code: UK
      # Automatically link email and phone or display as text?
      autolink: true
    design:
      columns: '2'
---
