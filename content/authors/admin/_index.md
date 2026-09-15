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

# Social/Academic Networking
# For available icons, see: https://wowchemy.com/docs/getting-started/page-builder/#icons
#   For an email link, use "fas" icon pack, "envelope" icon, and a link in the
#   form "mailto:your-email@example.com" or "/#contact" for contact widget.
social:
  - icon: envelope
    icon_pack: fas
    link: '/#contact'
  - icon: graduation-cap # Alternatively, use `google-scholar` icon from `ai` icon pack
    icon_pack: fas
    link: https://scholar.google.com/citations?hl=en&user=d0zu1QEAAAAJ&view_op=list_works&sortby=pubdate
  # Link to a PDF of your resume/CV.
  # To use: copy your resume to `static/uploads/resume.pdf`, enable `ai` icons in `params.yaml`,
  # and uncomment the lines below.


# Enter email to display Gravatar (if Gravatar enabled in Config)
email: 'o.robinson@ucl.ac.uk'

# Highlight the author in author lists? (true/false)
highlight_name: true
---
Oliver Robinson is a Professor of Neuroscience and Mental Health at the Institute of Cognitive Neuroscience, University College London. His primary focus is anxiety across adaptive and pathological states. He uses, among other things, computational psychiatry, neuroimaging and psychopharmacology. You can find a list of his papers below or on <a href="https://pubmed.ncbi.nlm.nih.gov/?term=Robinson%20OJ%20OR%2010.1093%2Fscan%2Fnsw088%20NOT%20%22Curtin%20University%22%20NOT%20%22Pregnancy%22%20NOT%20%22duck%22%20NOT%20%22turtle%22%20NOT%20%22Cornell%22" target="_blank" rel="noopener noreferrer">Pubmed</a> or <a href="https://scholar.google.com/citations?hl=en&user=d0zu1QEAAAAJ&view_op=list_works&sortby=pubdate" target="_blank" rel="noopener noreferrer">Google.</a> A recent profile of his work at UCL can be found <a href="https://www.ucl.ac.uk/mental-health/mental-health-awareness-week/professor-oliver-robinson-and-anxiety-lab" target="_blank" rel="noopener noreferrer">here.</a> For open science materials see Github, OSF, figshare and neurovault.

His first book for a public audience "The Anxious Brain" can be pre-ordered <a href="https://www.waterstones.com/book/the-anxious-brain/oliver-robinson/9780349447612" target="_blank" rel="noopener noreferrer">here</a>.

<div style="display:flex; gap:2rem; align-items:flex-start; flex-wrap:wrap; margin-top:1rem;">
  <div style="flex:1; min-width:200px;">
    <a href="https://www.waterstones.com/book/the-anxious-brain/oliver-robinson/9780349447612" target="_blank" rel="noopener noreferrer">
      <img src="9780349447612.jpg" alt="The Anxious Brain book cover" style="width:100%; max-width:250px; border-radius:8px;">
    </a>
  </div>
  <div style="flex:2; min-width:280px;">
    <iframe width="100%" height="250" src="https://www.youtube.com/embed/agmbSqNHUT4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
  </div>
</div>


<h2>Recent Publications</h2>
<div id="pubmed-feed" style="text-align:left; font-size:0.8rem;">Loading publications...</div>

<script>
fetch('https://api.rss2json.com/v1/api.json?rss_url=https://pubmed.ncbi.nlm.nih.gov/rss/search/14g2Xb2ijyNeeEEO6ebG1zkN-sxELinCWeFrnec35piXUc9k9l/?limit=100%26utm_campaign=pubmed-2%26fc=20260915102003&count=100')
  .then(r => r.json())
  .then(async data => {
    const container = document.getElementById('pubmed-feed');
    const ids = data.items.map(item => {
      const match = item.link.match(/\/(\d+)\//);
      return match ? match[1] : null;
    }).filter(Boolean).join(',');

    const apiUrl = `https://eutils.ncbi.nlm.nih.gov/entrez/eutils/esummary.fcgi?db=pubmed&id=${ids}&retmode=json`;
    const res = await fetch(apiUrl);
    const json = await res.json();

    container.innerHTML = data.items.map(item => {
      const match = item.link.match(/\/(\d+)\//);
      const pmid = match ? match[1] : null;
      const details = pmid && json.result[pmid];
      const authors = details ? details.authors.map(a => a.name).join(', ') : '';
      const journal = details ? details.fulljournalname : '';
      const year = item.pubDate ? item.pubDate.substring(0, 4) : '';
      return `
        <p style="margin-bottom:1.5rem; line-height:1.6; text-align:left;">
          <a href="${item.link}" target="_blank" rel="noopener noreferrer" style="font-weight:bold; text-decoration:none;">${item.title}</a>
          ${year ? `<span style="color:#666;"> (${year})</span>` : ''}
          <br>
          <span style="color:#444;">${authors}</span>
          <br>
          <em style="color:#666;">${journal}</em>
        </p>
      `;
    }).join('');
  })
  .catch(err => {
    document.getElementById('pubmed-feed').innerHTML = 'Could not load publications.';
    console.error(err);
  });
</script>
