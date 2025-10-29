<h1>GitPolish Pages Template Pack — v4.2.1</h1>
<p><strong>Profile:</strong> <code>leonidas-esquire</code> • Preset: <em>Lingua Obscurati</em></p>

<p>A batteries-included, multi-repo starter for GitHub Pages with shared theme/content, template-sync, auto-updates, and one-command bootstrapping—prefilled for <code>leonidas-esquire</code>.</p>

<hr />

<h2 id="repos">Repos in this preset</h2>
<ul>
  <li><strong>Portal (hub):</strong> <code>lingua-obscurati-portal</code> —
    <a href="https://leonidas-esquire.github.io/lingua-obscurati-portal/">live</a> •
    <a href="https://github.com/leonidas-esquire/lingua-obscurati-portal">repo</a>
  </li>
  <li><strong>Showcase (site):</strong> <code>lingua-obscurati-site</code> —
    <a href="https://leonidas-esquire.github.io/lingua-obscurati-site/">live</a> •
    <a href="https://github.com/leonidas-esquire/lingua-obscurati-site">repo</a>
  </li>
  <li><strong>Shared theme:</strong> <code>theme-shared-template</code> —
    <a href="https://github.com/leonidas-esquire/theme-shared-template">repo</a>
  </li>
  <li><strong>Shared content:</strong> <code>content-shared-template</code> —
    <a href="https://github.com/leonidas-esquire/content-shared-template">repo</a>
  </li>
</ul>

<hr />

<h2 id="what-you-get">What You Get</h2>
<ul>
  <li>🏛 Portal site template (lists showcases, blog/about optional)</li>
  <li>🎯 Showcase site template (single project/marketing)</li>
  <li>🎨 Shared theme (design tokens + UI partials via submodule)</li>
  <li>🧭 Shared content (brand/legal/snippets + consumer notifications)</li>
  <li>🤖 Workflows baked in: <code>pages.yml</code>, <code>update-submodules.yml</code>, <code>template-sync.yml</code>, <code>links.yml</code></li>
</ul>

<p><em>Project Pages–ready:</em> assets and JSON fetches use relative paths so pages render at <code>/&lt;REPO&gt;/</code> correctly.</p>

<hr />

<h2 id="quick-start">Quick Start (what to expect)</h2>
<ol>
  <li>Bootstrap scripts create the 4 repos under <code>leonidas-esquire</code>.</li>
  <li>Portal/showcase are set as <em>Template repositories</em>.</li>
  <li>Theme/content are added as submodules to both sites.</li>
  <li>First commit pushes; GitHub Pages deploys via <code>.github/workflows/pages.yml</code>.</li>
</ol>

<hr />

<h2 id="how-deploy-works">How Deploy Works</h2>
<ol>
  <li>Checkout with submodules (theme/content).</li>
  <li>Vendor shared assets at build time:
    <ul>
      <li>Tokens/UI from <code>theme-shared/</code> → <code>public/...</code></li>
      <li>Brand/legal/snippets from <code>content-shared/</code> → <code>public/...</code> and <code>docs/legal/</code></li>
    </ul>
  </li>
  <li>Upload <code>public/</code> artifact and deploy to GitHub Pages.</li>
</ol>

<hr />

<h2 id="sync-automation">Sync &amp; Automation</h2>
<h3>1) Shared submodules → weekly PRs</h3>
<p><code>update-submodules.yml</code> runs weekly and on <code>repository_dispatch</code> events (<code>content-release</code>, <code>theme-release</code>). It bumps submodules and opens a PR.</p>

<h3>2) Template sync from upstream</h3>
<p><code>template-sync.yml</code> pulls selected boilerplate paths (<code>.github/workflows</code>, <code>.editorconfig</code>, <code>.gitignore</code>, <code>README.md</code>, <code>CONTRIBUTING.md</code>, <code>SECURITY.md</code>) from an upstream template repo into a PR.</p>

<h3>3) Consumers (content → downstream notifications)</h3>
<p>In <strong>content-shared-template</strong>:</p>
<ul>
  <li><code>consumers.json</code> lists repos to notify (pre-filled with Lingua Obscurati sites).</li>
  <li><code>notify-consumers.yml</code> sends <code>repo_dispatch</code> to each consumer on content changes.</li>
</ul>

<h3>4) Broken links check</h3>
<p><code>links.yml</code> runs <em>Lychee</em> on a schedule and on demand.</p>

<hr />

<h2 id="requirements">Requirements</h2>
<ul>
  <li>Repo → Settings → Actions → General → Workflow permissions: <strong>Read and write</strong>.</li>
  <li>If shared repos are private, use a <code>SUBMODULE_TOKEN</code> secret in consumers and pass it to <code>actions/checkout</code> with <code>submodules: true</code>.</li>
</ul>

<hr />

<h2 id="troubleshooting">Troubleshooting</h2>
<ul>
  <li><strong>Assets 404/CSS missing:</strong> ensure pages use relative paths (fixed in v4.2.1 defaults).</li>
  <li><strong>Template-sync didn’t pull:</strong> confirm <code>env.TEMPLATE_REPO</code> and access; only the listed paths are synced.</li>
  <li><strong>Submodules didn’t update:</strong> verify Actions “Read &amp; write” and review the PR opened by <code>update-submodules.yml</code>.</li>
  <li><strong>Content dispatch not received:</strong> check <code>consumers.json</code> and the <code>ORG_BOT_TOKEN</code> secret (PAT with <code>repo</code> scope).</li>
</ul>

<hr />

<h2 id="changelog">Changelog</h2>
<ul>
  <li><strong>4.2.1</strong> — Relative paths for assets/JSON (Project Pages friendly)</li>
  <li><strong>4.2</strong> — Lingua Obscurati preset (slugs, favicon “LO”, seeded showcase list)</li>
  <li><strong>4.1</strong> — Prefilled org defaults; seeded <code>consumers.json</code>; streamlined bootstrap</li>
  <li><strong>4.0</strong> — Initial multi-repo pack: Pages CI, template-sync, shared theme/content</li>
</ul>

<hr />
