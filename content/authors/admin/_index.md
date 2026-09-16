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

# Interests to show in About widget
interests:
  - Mental Health
  - Computational Psychiatry
  - Neuroimaging
  - Psychopharmacology

# Education to show in About widget
education:
  courses:
    - course: PhD in Psychiatry
      institution: University of Cambridge
      year: 2009
    - course: BA Natural Sciences (Neuroscience)
      institution: University of Cambridge
      year: 2005

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
<div style="display:flex; gap:3rem; align-items:flex-start; flex-wrap:wrap; margin-top:1rem;">

  <div style="flex:1; min-width:280px;">

    <p>Oliver Robinson is a Professor of Neuroscience and Mental Health at the Institute of Cognitive Neuroscience, University College London. His primary focus is anxiety across adaptive and pathological states. He uses, among other things, computational psychiatry, neuroimaging and psychopharmacology. You can find a full list of his papers below or on <a href="https://pubmed.ncbi.nlm.nih.gov/?term=Robinson+OJ+OR+10.1093%2Fscan%2Fnsw088+NOT+%22Curtin+University%22+NOT+%22Pregnancy%22+NOT+%22duck%22+NOT+%22turtle%22+NOT+%22Cornell%22+NOT+%22SNAP%22+NOT+%22Robinson+OJK%22+NOT+%22Imperial%22&sort=date" target="_blank" rel="noopener noreferrer">Pubmed</a> or <a href="https://scholar.google.com/citations?hl=en&user=d0zu1QEAAAAJ&view_op=list_works&sortby=pubdate" target="_blank" rel="noopener noreferrer">Google.</a> A recent profile of his work at UCL can be found <a href="https://www.ucl.ac.uk/mental-health/mental-health-awareness-week/professor-oliver-robinson-and-anxiety-lab" target="_blank" rel="noopener noreferrer">here.</a> For open science materials see Github, OSF, figshare and neurovault.</p>

    <p>His first book for a public audience "The Anxious Brain" can be pre-ordered <a href="https://www.waterstones.com/book/the-anxious-brain/oliver-robinson/9780349447612" target="_blank" rel="noopener noreferrer">here</a>.</p>

    <div style="display:flex; gap:2rem; align-items:center; flex-wrap:wrap; margin-top:1rem;">
      <div style="flex:1; min-width:200px;">
        <a href="https://www.waterstones.com/book/the-anxious-brain/oliver-robinson/9780349447612" target="_blank" rel="noopener noreferrer">
          <img src="/9780349447612.jpg" alt="The Anxious Brain book cover" style="width:100%; max-width:250px; border-radius:8px;">
        </a>
      </div>
      <div style="flex:2; min-width:280px;">
        <iframe width="100%" height="250" src="https://www.youtube.com/embed/agmbSqNHUT4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
      </div>
    </div>

  </div>

  <div style="flex:1; min-width:280px;">
    <h2>Recent Publications</h2>
    <div id="pubmed-feed" style="text-align:left; font-size:0.7rem; max-height:80vh; overflow-y:auto;">Loading publications...</div>
  </div>

</div>

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
        <span style="color:#444;">${item.author}</span>
        <br>
        <em style="color:#666;">${item.journal}</em>
      </p>
    `).join('');
  })
  .catch(err => {
    document.getElementById('pubmed-feed').innerHTML = 'Could not load publications. Error: ' + err.message;
  });
</script>
