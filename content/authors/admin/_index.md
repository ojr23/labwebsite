---
# Display name
title: Oliver Robinson

# Full name (for SEO)
first_name: Oliver 
last_name: Robinson

# Status emoji
status:
  icon: 

# Is this the primary user of the site?
superuser: true

# Role/position/tagline
role: Professor of Neuroscience and Mental Health

# Organizations/Affiliations to show in About widget
organizations:
  - name: University College London
    url: https://www.ucl.ac.uk/icn/research/research-groups/neuroscience-and-mental-health

# Short bio (displayed in user profile at end of posts)
bio: My research interests include mental health, anxiety, computational psychiatry, neuroimaging, psychopharmacology

social:
  - icon: envelope
    icon_pack: fas
    link: '/#contact'
  - icon: graduation-cap
    icon_pack: fas
    link: https://scholar.google.com/citations?hl=en&user=d0zu1QEAAAAJ&view_op=list_works&sortby=pubdate

email: 'o.robinson@ucl.ac.uk'
highlight_name: true
---

<p style="text-align:left;">Oliver Robinson is a Professor of Neuroscience and Mental Health at the Institute of Cognitive Neuroscience, University College London where he co-directs the <a href="https://www.ucl.ac.uk/icn/research/research-groups/neuroscience-and-mental-health" target="_blank" rel="noopener noreferrer">Neuroscience and Mental Health Group</a>. His primary focus is anxiety across adaptive and pathological states. He uses, among other things, computational psychiatry, neuroimaging and psychopharmacology. 
  
<p style="text-align:left;">You can find his most recent scientific papers below or an exhaustive list on <a href="https://pubmed.ncbi.nlm.nih.gov/?term=Robinson+OJ+OR+10.1093%2Fscan%2Fnsw088+NOT+%22Curtin+University%22+NOT+%22Pregnancy%22+NOT+%22duck%22+NOT+%22turtle%22+NOT+%22Cornell%22+NOT+%22SNAP%22+NOT+%22Robinson+OJK%22+NOT+%22Imperial%22&sort=date" target="_blank" rel="noopener noreferrer">Pubmed</a>, <a href="https://scholar.google.com/citations?hl=en&user=d0zu1QEAAAAJ&view_op=list_works&sortby=pubdate" target="_blank" rel="noopener noreferrer">Google</a>, or <a href="https://profiles.ucl.ac.uk/40163-oliver-robinson" target="_blank" rel="noopener noreferrer">UCL.</a> You can find  a UCL Podcast about his work <a href="https://www.youtube.com/watch?v=Yu2NCar2bJM" target="_blank" rel="noopener noreferrer">here</a>. For open science materials see Github, OSF, figshare and neurovault.</p>

<p style="text-align:left;">His first book for a public audience "The Anxious Brain" can be pre-ordered <a href="https://www.waterstones.com/book/the-anxious-brain/oliver-robinson/9780349447612" target="_blank" rel="noopener noreferrer">here</a>. He is represented by <a href="https://lutyensrubinstein.co.uk/authors/oliver-robinson" target="_blank" rel="noopener noreferrer">Lutyens & Rubinstein Literary Agency</a>.</p>

<div style="display:flex; gap:2rem; align-items:center; flex-wrap:wrap; margin-top:1rem; margin-bottom:3rem;">
  <div style="flex:1; min-width:200px;">
    <a href="https://www.waterstones.com/book/the-anxious-brain/oliver-robinson/9780349447612" target="_blank" rel="noopener noreferrer">
      <img src="/9780349447612.jpg" alt="The Anxious Brain book cover" style="width:100%; max-width:250px; border-radius:8px;">
    </a>
  </div>
  <div style="flex:2; min-width:280px;">
    <iframe width="100%" height="250" src="https://www.youtube.com/embed/agmbSqNHUT4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
  </div>
</div>

<hr style="border:none; border-top:1px solid #eee; margin:2rem 0;">

<h2 style="text-align:left; font-size:1.5rem; margin-bottom:1.5rem;">Recent Publications</h2>
<div id="pubmed-feed" style="text-align:left; font-size:0.7rem;">Loading publications...</div>

<script>
fetch('/publications.json')
  .then(r => r.json())
  .then(items => {
    const container = document.getElementById('pubmed-feed');
    if (!items || items.length === 0) {
      container.innerHTML = 'No publications found.';
      return;
    }
    container.innerHTML = items.map(item => `
      <p style="margin-bottom:1.5rem; line-height:1.6; text-align:left;">
        ${item.link 
          ? `<a href="${item.link}" target="_blank" rel="noopener noreferrer" style="font-weight:bold; text-decoration:none;">${item.title}</a>`
          : `<strong>${item.title}</strong>`}
        ${item.year ? `<span style="color:#666;"> (${item.year})</span>` : ''}
        <br>
        <span style="color:#444;">${item.author.replace(/Robinson OJ?/g, '<strong>Robinson OJ</strong>')}</span>
        <br>
        <em style="color:#666;">${item.journal}</em>
      </p>
    `).join('');
  })
  .catch(err => {
    document.getElementById('pubmed-feed').innerHTML = 'Could not load publications. Error: ' + err.message;
  });
</script>
