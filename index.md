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
  color: #111;
  line-height: 1.6;
}

main {
  max-width: 900px;
  margin: auto;
  padding: 60px 20px;
}

h1 {
  font-size: 2.4rem;
  margin-bottom: 0.2em;
}

h2 {
  margin-top: 70px;
  font-size: 1.4rem;
  border-bottom: 1px solid #eaeaea;
  padding-bottom: 8px;
}

.hero-sub {
  color: #555;
  margin-bottom: 40px;
}

a {
  color: #111;
  text-decoration: none;
  border-bottom: 1px solid #ccc;
}

a:hover {
  border-bottom: 1px solid #111;
}

.project {
  margin-top: 50px;
}

.project img {
  width: 100%;
  border-radius: 6px;
  margin: 15px 0;
}

.compact {
  margin-top: 20px;
}

.logo {
  width: 85px;
  margin-top: 20px;
}

.grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 15px;
  margin-top: 20px;
}

.grid img {
  width: 100%;
  border-radius: 6px;
}

@media (max-width: 700px) {
  .grid { grid-template-columns: 1fr; }
}
</style>
</head>

<body>
<main>

<h1>Rûmeysa CAN</h1>
<div class="hero-sub">
Modélisation computationnelle des systèmes biologiques et neuronaux<br>
Transcriptomique single-cell · Traitement du signal
</div>

<h2>Projets</h2>

<div class="project">
<h3>Transcriptomique single-cell</h3>
<p>QC → normalisation → PCA → Leiden → UMAP (Scanpy)</p>
<img src="assets/projects/scRNAseq_umap.png">
<p>6 clusters identifiés</p>
<a href="https://github.com/uruys/Analyse-cell-rnaseq" target="_blank">GitHub</a>
</div>

<div class="project">
<h3>PRDM1 & Lupus — RNA-seq</h3>
<p>DESeq2 · correction FDR · réseau STRING</p>
<img src="assets/projects/volcano_prdm1.png">
<p>PRDM1 identifié comme gène hub</p>
<a href="https://github.com/uruys/Bioinformatics_Lupus_PRDM1" target="_blank">GitHub</a>
</div>

<div class="project">
<h3>Analyse EEG</h3>
<p>Filtrage · FFT · analyse spectrale</p>
<img src="assets/projects/eeg_spectrogram.png">
<p>Augmentation β/γ en condition pathologique</p>
<a href="https://github.com/uruys/eeg-neuroscience-analyse" target="_blank">GitHub</a>
</div>

<div class="compact">
<strong>SARS-CoV-2 — Surveillance eaux usées</strong><br>
Séries temporelles · signal précurseur<br>
<a href="https://github.com/uruys/Projet_Biocapteurs" target="_blank">GitHub</a>
</div>

<div class="compact">
<strong>Tracking comportemental — DeepLabCut</strong><br>
Extraction métriques cinématiques<br>
<a href="https://github.com/uruys/computational-neuroscience-analysis" target="_blank">GitHub</a>
</div>

<h2>Expériences</h2>

<img src="assets/logos/bme-lab.png" class="logo">
<p><strong>BME Lab — Hôpital Saint-Joseph</strong><br>
Données cliniques OMOP-CDM · R / Python</p>

<img src="assets/logos/neuropsi.png" class="logo">
<p><strong>NeuroPSI — CNRS Paris-Saclay</strong><br>
DeepLabCut · Électrophysiologie</p>

<h2>Formation</h2>

<img src="assets/logos/sorbonne-paris-nord.png" class="logo">
<p><strong>Licence Sciences de la Vie</strong><br>
Université Sorbonne Paris Nord</p>

<img src="assets/logos/lycee-geoffroy.png" class="logo">
<p><strong>Baccalauréat Général</strong><br>
Lycée Geoffroy Saint-Hilaire</p>

<h2>Photos</h2>
<div class="grid">
<img src="assets/photos/photo-01.jpg">
<img src="assets/photos/photo-02.jpg">
<img src="assets/photos/photo-03.jpg">
</div>

<h2>Lecture</h2>
<div class="grid">
<img src="assets/lecture/livre-01.png">
<img src="assets/lecture/livre-02.png">
<img src="assets/lecture/livre-03.png">
<img src="assets/lecture/livre-04.png">
</div>

<h2>Certifications</h2>
<div class="grid">
<a href="https://coursera.org/verify/TH0C8OXJ3HGD" target="_blank">
<img src="assets/certifications/coursera-computational-neuroscience.png">
</a>
<a href="https://coursera.org/verify/ZHX2R66XPODU" target="_blank">
<img src="assets/certifications/coursera-calculus-ml.png">
</a>
<a href="https://courses.cognitiveclass.ai/certificates/56117e580a0a4deea692c45ce0ff9322" target="_blank">
<img src="assets/certifications/ibm-sql.png">
</a>
</div>

</main>
</body>
</html>
