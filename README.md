<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>SF Crime: Two Decades of Data</title>
  <style>
    :root {
      --bg: #433232;
      --panel: #664B4B;
      --panel-hover: #785959;
      --text: #E8E3E3;
      --muted: #CABEBE;
      --accent: #9C241E;
      --accent-dark: #631713;
      --border: rgba(255, 255, 255, 0.08);
      --shadow: 0 10px 30px rgba(0, 0, 0, 0.25);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      font-family: Arial, Helvetica, sans-serif;
      background: var(--bg);
      color: var(--text);
      line-height: 1.6;
    }

    .container {
      width: min(1100px, 92%);
      margin: 0 auto;
    }

    header {
      width: 100%;
      padding: 4.5rem 0 3rem;
      /*background: linear-gradient(180deg, rgba(22, 199, 154, 0.08), rgba(26, 26, 46, 0));*/
      border-bottom: 1px solid var(--border);
    }

    .header-inner {
      max-width: 800px;
    }

    h1 {
      font-size: clamp(2rem, 5vw, 3.5rem);
      line-height: 1.15;
      margin-bottom: 1rem;
      color: var(--text);
    }

    .accent {
      color: var(--accent);
    }

    .intro {
      font-size: 1.05rem;
      color: var(--muted);
      max-width: 70ch;
    }

    main {
      padding: 2.5rem 0 4rem;
    }

    .section-title {
      font-size: 1.4rem;
      margin-bottom: 1.25rem;
      color: var(--accent);
    }

    .card-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
      gap: 1.25rem;
    }

    .card {
      background: var(--panel);
      border: 1px solid var(--border);
      border-radius: 16px;
      padding: 1.25rem;
      box-shadow: var(--shadow);
      transition: transform 0.25s ease, box-shadow 0.25s ease, background 0.25s ease, border-color 0.25s ease;
    }

    .card:hover {
      transform: translateY(-6px);
      background: var(--panel-hover);
      border-color: #F29696;
      box-shadow: 0 16px 36px rgba(0, 0, 0, 0.35);
    }

    .card h3 {
      font-size: 1.15rem;
      margin-bottom: 0.5rem;
      color: var(--text);
    }

    .card p {
      font-size: 0.97rem;
      color: var(--muted);
      margin-bottom: 1rem;
    }

    .card a {
      display: inline-block;
      color: #fff;
      text-decoration: none;
      font-weight: 600;
      transition: color 0.2s ease, transform 0.2s ease;
    }

    .card a:hover {
      color: #D9A65F;
      transform: translateX(2px);
    }

    footer {
      padding: 1.5rem 0 2.5rem;
      color: var(--muted);
      font-size: 0.9rem;
      border-top: 1px solid var(--border);
    }

    @media (max-width: 600px) {
      header {
        padding: 3.25rem 0 2.25rem;
      }

      .card {
        padding: 1rem;
      }

      .intro {
        font-size: 1rem;
      }
    }
      .viz-section {
  margin-top: 3rem;
}

.viz-grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2rem;
  align-items: center;
}

.viz-plot {
  background: #22223b;
  padding: 1rem;
  border-radius: 12px;
  border: 1px solid rgba(255,255,255,0.08);
}

.viz-plot img,
.viz-plot iframe {
  width: 100%;
  height: 400px;
  border: none;
  border-radius: 8px;
}

.viz-text {
  color: #c9d1d9;
}

.viz-text h3 {
  color: #16c79a;
  margin-bottom: 0.5rem;
}

.viz-text p {
  margin-bottom: 1rem;
}

/* Mobile */
@media (max-width: 768px) {
  .viz-grid {
    grid-template-columns: 1fr;
  }

  .viz-plot iframe,
  .viz-plot img {
    height: 300px;
  }
}
.viz-section {
      margin: 3rem auto;
      padding: 2rem;
      background: #22223b;
      border-radius: 16px;
      max-width: 1000px;
    }

    .viz-grid {
      display: flex;
      flex-direction: column;
      align-items: center;
      text-align: center;
    }

    .viz-plot {
      max-width: 800px;
      width: 100%;
      margin: 1rem auto;
    }

    .viz-plot img,
    .viz-plot iframe {
      width: 100%;
      height: auto;
      border-radius: 10px;
    }

      /* Images (bar plot) */
      .viz-plot img {
          width: 100%;
          height: auto;
          border-radius: 10px;
      }
      
      /* Heatmap (iframe) */
      .viz-plot iframe {
          width: 100%;
          height: 600px;   /* 👈 THIS CONTROLS SIZE */
          border: none;
          border-radius: 10px;
      }
      

    .viz-text {
      max-width: 700px;
      margin: 1rem auto;
      color: #c9d1d9;
    }
  </style>
</head>
<body>
  <header>
    <div class="container header-inner">
      <h1>SF Crime: <span class="accent">Two Decades of Data</span></h1>
      <p class="intro">
        This portfolio explores patterns, shifts, and hotspots in San Francisco crime data across the last twenty years. 
        It brings together interactive visuals and focused analyses to show how crime changes over time, across neighborhoods, and by offense type.
      </p>
    </div>
  </header>

  <main>
    <div class="container">
      <h2 class="section-title">Portfolio Projects</h2>

      <section class="card-grid">
        <article class="card">
          <h3>Crime Trends Over Time</h3>
          <p>A year-by-year view of how reported crime has changed across two decades.</p>
          <a href="#">View analysis</a>
        </article>

        <article class="card">
          <h3>Neighborhood Hotspots</h3>
          <p>An interactive map highlighting where crime is most concentrated in the city.</p>
          <a href="#">Explore map</a>
        </article>

        <article class="card">
          <h3>Category Breakdown</h3>
          <p>A comparison of major offense types and how their patterns differ over time.</p>
          <a href="#">See categories</a>
        </article>

        <article class="card">
          <h3>Seasonal Patterns</h3>
          <p>A look at how crime varies by month, season, and recurring annual cycles.</p>
          <a href="#">Open chart</a>
        </article>

        <article class="card">
          <h3>Day and Hour Analysis</h3>
          <p>A timeline of when incidents are most likely to happen during the week.</p>
          <a href="#">View timing data</a>
        </article>

        <article class="card">
          <h3>District Comparison</h3>
          <p>A side-by-side overview of crime levels across police districts in San Francisco.</p>
          <a href="#">Compare districts</a>
        </article>
      </section>
    </div>
  </main>

 <section class="viz-section">
  <h2 style="color:#16c79a;">Bar Plot Analysis</h2>

  <div class="viz-grid">

    <!-- PLOT -->
    <div class="viz-plot">
      <img src="images/distribution.svg" alt="Bar plot">
    </div>

    <!-- TEXT -->
    <div class="viz-text">
      <h3>Insights</h3>
      <p>
        This bar plot shows the distribution of crime categories in San Francisco.
        Theft-related crimes dominate, followed by assault and burglary.
      </p>
    </div>

  </div>
</section>


<section class="viz-section">
  <h2 style="color:#16c79a;">Heatmap Analysis</h2>

  <div class="viz-grid">

    <!-- PLOT -->
    <div class="viz-plot">
      <iframe src="visualisations/SF_prost_map.html"></iframe>
    </div>

    <!-- TEXT -->
    <div class="viz-text">
      <h3>Insights</h3>
      <p>
        The heatmap shows where crime is concentrated across San Francisco.
        Clear hotspots appear in central and high-activity areas.
      </p>
    </div>

  </div>
</section>
  <footer>
    <div class="container">
      Data science portfolio focused on long-term crime patterns in San Francisco.
    </div>
  </footer>
</body>
</html>
