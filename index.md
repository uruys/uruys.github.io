<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Rûmeysa CAN — Portfolio</title>

<style>
  body {
    font-family: -apple-system, BlinkMacSystemFont, sans-serif;
    margin: 0;
    background: #ffffff;
    color: #1a1a1a;
    line-height: 1.6;
  }
  main {
    max-width: 900px;
    margin: auto;
    padding: 40px 20px;
  }
  h1 { font-size: 2.2rem; margin-bottom: 0.3em; }
  h2 {
    margin-top: 60px;
    font-size: 1.5rem;
    border-bottom: 1px solid #eaeaea;
    padding-bottom: 10px;
  }
  .hero-sub { color: #555; font-size: 1rem; margin-bottom: 30px; }
  .research-focus ul { padding-left: 20px; }

  .logo { width: 80px; height: 80px; object-fit: contain; }
  .stage-logo { width: 90px; height: 90px; object-fit: contain; }

  .project { margin-top: 40px; }
  .project img { width: 100%; border-radius: 6px; margin: 15px 0; }

  .compact-project { margin-top: 18px; }
  .compact-project strong { display: inline-block; margin-bottom: 4px; }

  .grid-3 {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 15px;
    margin-top: 15px;
  }
  .grid-3 img { width: 100%; border-radius: 6px; }

  @media (max-width: 700px) { .grid-3 { grid-template-columns: 1fr; } }
</style>
</head>

<body>
<main>

  <!-- HERO -->
  <h1>Rûmeysa CAN</h1>
  <div class="hero-sub">
    Modélisation computationnelle des systèmes biologiques et neuronaux<br>
    Transcriptomique single-cell · Traitement du signal
  </div>

  <h2>Axes</h2>
  <div class="research-focus">
    <ul>
      <li>Transcriptomique single-cell et hétérogénéité cellulaire</li>
      <li>Traitement du signal neuronal et modélisation computationnelle</li>
    </ul>
  </div>

  <h2>Projets</h2>

  <div class="project">
    <h3>Transcriptomique single-cell — Identification de populations cellulaires</h3>
    <p><strong>Méthode :</strong> QC → normalisation → PCA → Leiden → UMAP (Scanpy)</p>
    <img src="assets/projects/scRNAseq_umap.png" alt="UMAP scRNA-seq">
    <p><strong>Résultat :</strong> 6 clusters identifiés</p>
    <a href="https://github.com/uruys/Analyse-cell-rnaseq" target="_blank" rel="noopener">GitHub</a>
  </div>

  <div class="project">
    <h3>PRDM1 & Lupus — Analyse différentielle RNA-seq</h3>
    <p><strong>Méthode :</strong> DESeq2 · correction FDR · réseau STRING</p>
    <img src="assets/projects/volcano_prdm1.png" alt="Volcano plot">
    <p><strong>Résultat :</strong> PRDM1 identifié comme gène hub</p>
    <a href="https://github.com/uruys/Bioinformatics_Lupus_PRDM1" target="_blank" rel="noopener">GitHub</a>
  </div>

  <div class="project">
    <h3>Analyse EEG — Normal vs crise épileptique</h3>
    <p><strong>Méthode :</strong> filtrage · FFT · puissance par bandes</p>
    <img src="assets/projects/eeg_spectrogram.png" alt="Analyse EEG">
    <p><strong>Résultat :</strong> augmentation β/γ</p>
    <a href="https://github.com/uruys/eeg-neuroscience-analyse" target="_blank" rel="noopener">GitHub</a>
  </div>

  <!-- Projets en compact (sans étiquette “autres”) -->
  <div class="compact-project">
    <strong>Surveillance SARS-CoV-2 (eaux usées)</strong><br>
    Séries temporelles · signal précurseur ~5 jours<br>
    <a href="https://github.com/uruys/Projet_Biocapteurs" target="_blank" rel="noopener">GitHub</a>
  </div>

  <div class="compact-project">
    <strong>Tracking comportemental — DeepLabCut</strong><br>
    Extraction métriques cinématiques · réduction annotation manuelle<br>
    <a href="https://github.com/uruys/computational-neuroscience-analysis" target="_blank" rel="noopener">GitHub</a>
  </div>

  <h2>Expériences</h2>

  <img src="assets/logos/bme-lab.png" class="stage-logo" alt="BME Lab">
  <p><strong>BME Lab — Hôpital Saint-Joseph</strong><br>
    Données cliniques (OMOP-CDM) · R / Python
  </p>

  <img src="assets/logos/neuropsi.png" class="stage-logo" alt="NeuroPSI">
  <p><strong>NeuroPSI — CNRS Paris-Saclay</strong><br>
    DeepLabCut · Électrophysiologie · Imagerie GCaMP
  </p>

  <h2>Formation</h2>

  <img src="assets/logos/sorbonne-paris-nord.png" class="logo" alt="Université Sorbonne Paris Nord">
  <p><strong>Licence Sciences de la Vie</strong><br>Université Sorbonne Paris Nord</p>

  <img src="assets/logos/lycee-geoffroy.png" class="logo" alt="Lycée Geoffroy Saint-Hilaire">
  <p><strong>Baccalauréat Général</strong><br>Lycée Geoffroy Saint-Hilaire</p>

  <h2>Photos</h2>
  <div class="grid-3">
    <img src="assets/photos/photo-01.jpg" alt="Photo 1">
    <img src="assets/photos/photo-02.jpg" alt="Photo 2">
    <img src="assets/photos/photo-03.jpg" alt="Photo 3">
  </div>

  <h2>Lecture</h2>
  <div class="grid-3">
    <img src="assets/lecture/livre-01.png" alt="Activer ses neurones — Steve Masson">
    <img src="assets/lecture/livre-02.png" alt="Sciences & éthique — Gérard Toulouse">
    <img src="assets/lecture/livre-03.png" alt="Quelle éthique pour les sciences ?">
  </div>
  <div class="grid-3">
    <img src="assets/lecture/livre-04.png" alt="L’intelligence naturelle et l’éveil de la conscience — Antonio Damasio">
  </div>

  <h2>Certifications</h2>
  <div class="grid-3">
    <a href="https://coursera.org/verify/TH0C8OXJ3HGD" target="_blank" rel="noopener">
      <img src="assets/certifications/coursera-computational-neuroscience.png" alt="Coursera — Computational Neuroscience">
    </a>
    <a href="https://coursera.org/verify/ZHX2R66XPODU" target="_blank" rel="noopener">
      <img src="assets/certifications/coursera-calculus-ml.png" alt="Coursera — Calculus for ML">
    </a>
    <a href="https://courses.cognitiveclass.ai/certificates/56117e580a0a4deea692c45ce0ff9322" target="_blank" rel="noopener">
      <img src="assets/certifications/ibm-sql.png" alt="IBM — SQL and Relational Databases 101">
    </a>
  </div>

</main>
</body>
</html>
