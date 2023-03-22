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
    design:
      columns: '2'
      view: citation
  - block: markdown
    content:
      title: Publications
      subtitle: My subtitle
      text: <iframe src="http://research-reports.ucl.ac.uk/RPSDATA.SVC/pubs/OROBI05"></iframe>
    design:
      # See Page Builder docs for all section customization options.
      # Choose how many columns the section has. Valid values: '1' or '2'.
      columns: '1'      
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
