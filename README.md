Here is an HTML document that provides slide-by-slide explanatory summaries for each session and topic from your BAHS 201 course materials.

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BAHS 201 | Biochemistry & Molecular Cell Biology: Slide-by-Slide Summaries</title>
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,500;14..32,600;14..32,700&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: #f1f5f9;
            color: #0a2540;
            line-height: 1.5;
            padding: 2rem 1.5rem;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
        }

        /* header */
        .hero {
            background: linear-gradient(135deg, #0b2b3b 0%, #1b4a6e 100%);
            color: white;
            border-radius: 2rem;
            padding: 2.5rem 2rem;
            margin-bottom: 2.5rem;
            box-shadow: 0 10px 25px -5px rgba(0,0,0,0.1);
        }

        .hero h1 {
            font-size: 2.2rem;
            font-weight: 700;
            letter-spacing: -0.01em;
            margin-bottom: 0.5rem;
        }

        .hero p {
            font-size: 1.1rem;
            opacity: 0.85;
            max-width: 700px;
        }

        .badge {
            background: #ffb347;
            color: #1e2f3a;
            padding: 0.2rem 0.7rem;
            border-radius: 40px;
            font-size: 0.75rem;
            font-weight: 600;
            display: inline-block;
            margin-top: 1rem;
        }

        /* session accordion style */
        .sessions-grid {
            display: flex;
            flex-direction: column;
            gap: 1.5rem;
        }

        .session-card {
            background: white;
            border-radius: 1.5rem;
            overflow: hidden;
            box-shadow: 0 4px 12px rgba(0,0,0,0.05);
            transition: all 0.2s ease;
            border: 1px solid #e2edf2;
        }

        .session-header {
            background: #ffffff;
            padding: 1.2rem 1.8rem;
            cursor: pointer;
            display: flex;
            justify-content: space-between;
            align-items: center;
            border-bottom: 2px solid #e6f0f5;
            transition: background 0.2s;
        }

        .session-header:hover {
            background: #fafdff;
        }

        .session-title {
            font-weight: 700;
            font-size: 1.3rem;
            color: #1c6e8f;
        }

        .session-number {
            background: #e0f0f7;
            color: #0f5b7a;
            padding: 0.2rem 0.8rem;
            border-radius: 30px;
            font-size: 0.75rem;
            font-weight: 600;
            margin-right: 1rem;
        }

        .toggle-icon {
            font-size: 1.6rem;
            font-weight: 300;
            color: #5c8ea0;
        }

        .session-content {
            display: none;
            padding: 1.2rem 1.8rem 2rem 1.8rem;
            background: #fefefe;
            border-top: 1px solid #e9f0f4;
        }

        .session-content.open {
            display: block;
        }

        .learning-targets {
            background: #eef6fb;
            padding: 1rem 1.4rem;
            border-radius: 1rem;
            margin-bottom: 1.8rem;
            font-size: 0.9rem;
            border-left: 5px solid #2c7da0;
        }

        .slide-summary {
            margin-bottom: 1.5rem;
            border-bottom: 1px dashed #cbdbe2;
            padding-bottom: 1rem;
        }

        .slide-summary:last-child {
            border-bottom: none;
        }

        .slide-title {
            font-weight: 700;
            font-size: 1rem;
            color: #155f7c;
            background: #f0f9ff;
            display: inline-block;
            padding: 0.2rem 0.8rem;
            border-radius: 20px;
            margin-bottom: 0.6rem;
        }

        .slide-desc {
            color: #1a3b4b;
            margin-left: 0.3rem;
            font-size: 0.94rem;
            line-height: 1.45;
        }

        .key-term {
            background: #f4e6d2;
            color: #7a5300;
            padding: 0.1rem 0.3rem;
            border-radius: 8px;
            font-size: 0.85rem;
            font-weight: 500;
        }

        hr {
            margin: 0.8rem 0;
            border-color: #e2edf2;
        }

        footer {
            margin-top: 3rem;
            text-align: center;
            font-size: 0.85rem;
            color: #4b6f82;
            border-top: 1px solid #cbdde6;
            padding-top: 2rem;
        }

        @media (max-width: 700px) {
            body {
                padding: 1rem;
            }
            .session-title {
                font-size: 1rem;
            }
            .hero h1 {
                font-size: 1.6rem;
            }
        }
    </style>
</head>
<body>
<div class="container">
    <div class="hero">
        <h1>🧬 BAHS 201 · Basic Biochemistry & Molecular Cell Biology</h1>
        <p>Slide-by-slide explanatory summaries — DNA replication, signalling, transcription, repair, cloning, PCR and more.<br>Lecturer: Dr. D. K. Konlan, Esq.</p>
        <div class="badge">📚 13 sessions | core molecular concepts + clinical applications</div>
    </div>

    <div class="sessions-grid" id="sessionsGrid">
        <!-- content will be generated via JS -->
    </div>
    <footer>
        📖 Based on lecture slides (Sessions 1–12) & course guide · Summaries for study & revision · BAHS 2026
    </footer>
</div>

<script>
    // Data structure: each session: number, title, learningOutcomes (array), slidesSummaries (array of {title, description})
    const sessionsData = [
        { num: "01", title: "Introduction to Cell Signalling", outcomes: ["Identify components of cell signaling pathways", "Differentiate types of cellular communication (autocrine, paracrine, endocrine, synaptic)"],
          slides: [
              { t: "Overview / Cell signaling definition", d: "Cells monitor environment and respond via signaling molecules. Signaling cells release ligands that bind receptors on target cells → signal transduction pathway."},
              { t: "Signal propagation mechanisms", d: "Direct contact (membrane-bound signal), autocrine (self-signaling, e.g., growth factors), paracrine (nearby cells), endocrine (distant via blood), synaptic (neurons)."},
              { t: "Reception–Transduction–Response", d: "Reception: target detects signal. Transduction: receptor activates relay molecules. Response: cellular change (catalysis, gene activation)."},
              { t: "Signal transduction features", d: "Amplification: small signal → large response. Receptors: G-protein-linked, enzyme-linked, ion-channel. Ligands: first messengers."}
          ] },
        { num: "02", title: "Cell Membrane Receptors", outcomes: ["Explain main classes of membrane receptors", "Describe RTK mechanism", "G-protein-coupled receptors (GPCRs)", "Non-receptor tyrosine kinase (NRTK) pathways"],
          slides: [
              { t: "GPCR structure", d: "7 transmembrane α-helices, extracellular ligand-binding, intracellular G-protein coupling. G-protein (α,β,γ) binds GDP/GTP — molecular switch."},
              { t: "GPCR activation cycle", d: "Ligand binding → GDP→GTP exchange → α-GTP dissociates from βγ → activates effector (adenylyl cyclase, PLC). GTP hydrolysis returns to inactive."},
              { t: "Receptor Tyrosine Kinase (RTK)", d: "Extracellular binding, single TM domain, intrinsic tyrosine kinase. Dimerization upon ligand → autophosphorylation → docking sites for signaling proteins."},
              { t: "Non-receptor tyrosine kinase (JAK-STAT)", d: "Receptors lack kinase domain, recruit JAK. Cytokine binding → JAK phosphorylates receptor & STAT → STAT dimers translocate to nucleus → gene regulation."}
          ] },
        { num: "03", title: "Second Messengers & Intracellular Receptors", outcomes: ["Identify second messenger systems", "Compare cAMP, IP₃/DAG pathways", "Apply to hormonal/drug action"],
          slides: [
              { t: "G-protein pathways: cAMP", d: "Gs stimulates adenylyl cyclase → cAMP → activates PKA → phosphorylates metabolic enzymes/CREB → gene expression & glycogen breakdown."},
              { t: "Phospholipase C pathway (IP₃/DAG)", d: "Gq activates PLC → PIP₂ cleaved into IP₃ (Ca²⁺ release from ER) and DAG (activates PKC). Ca²⁺ + DAG → PKC → cellular responses."},
              { t: "Calmodulin & Ca²⁺ signaling", d: "Ca²⁺ binds calmodulin (CaM) → activates kinases (CaMK) and other effectors. Mediates inflammation, metabolism, apoptosis."},
              { t: "Intracellular receptors (steroid/thyroid)", d: "Lipophilic ligands cross membrane, bind cytosolic/nuclear receptors → receptor dimerizes → binds HRE → modulates transcription."}
          ] },
        { num: "04", title: "Central Dogma & Nucleic Acids", outcomes: ["Genetic basis of life", "DNA/RNA structure", "Nucleosides vs nucleotides", "Why DNA has T not U"],
          slides: [
              { t: "DNA & RNA chemistry", d: "Nucleotides = base (purine/pyrimidine) + pentose (ribose/deoxyribose) + phosphate. Nucleoside lacks phosphate. Phosphodiester bonds link 5'→3'."},
              { t: "Watson-Crick double helix", d: "Antiparallel strands, complementary base pairing (A=T, G≡C), 10 bp/turn, major/minor grooves, H-bonds and stacking."},
              { t: "Why thymine instead of uracil", d: "Cytosine deamination generates uracil; if DNA used U, repair would be ambiguous. Thymine allows recognition and repair of deaminated C."},
              { t: "Telomeres and aging", d: "Telomeres (TTAGGG repeats) protect chromosome ends. Somatic cells lack telomerase → telomeres shorten with age. Germ/stem cells express telomerase."}
          ] },
        { num: "05", title: "DNA Replication", outcomes: ["Essentials of replication", "E. coli replication", "Eukaryotic replication differences"],
          slides: [
              { t: "Meselson-Stahl & Cairns", d: "Semiconservative replication proven by density gradient. Cairns showed E. coli chromosome is circular, bidirectional origin, replication fork."},
              { t: "DNA polymerases & fidelity", d: "Pol III main replicase; Pol I removes primers. 5'→3' synthesis, requires primer. 3'→5' exonuclease proofreading reduces errors to 10⁻⁹."},
              { t: "Semidiscontinuous replication", d: "Leading strand continuous, lagging strand via Okazaki fragments (RNA primers). Primase, helicase, SSB, gyrase, ligase."},
              { t: "Telomerase mechanism", d: "Telomerase (reverse transcriptase with RNA template) adds TTAGGG repeats to solve end-replication problem. Linked to cellular aging & cancer."}
          ] },
        { num: "06", title: "DNA Damage and Repair", outcomes: ["Main ways of DNA damage", "Repair processes (BER, NER, direct reversal, mismatch)"],
          slides: [
              { t: "Spontaneous & induced damage", d: "Depurination (10⁴/day), deamination (C→U), oxidation (ROS), alkylation, UV-induced thymine dimers (cyclobutane, 6-4 PP)."},
              { t: "Base excision repair (BER)", d: "DNA glycosylase removes damaged base → AP endonuclease cuts backbone → Pol β fills gap → ligase seals. Targets uracil, 8-oxoG, etc."},
              { t: "Nucleotide excision repair (NER)", d: "Removes bulky lesions (cyclobutane dimers). XP proteins, TFIIH cut around damage → Pol δ/ε resynthesizes. Defects cause xeroderma pigmentosum."},
              { t: "Direct reversal & mismatch repair", d: "Photolyase (not in humans) splits dimers. MGMT removes methyl groups from O⁶-G. MMR corrects replication errors (mutS/mutL)."}
          ] },
        { num: "07", title: "Transcription", outcomes: ["Explain DNA→RNA transcription", "Requirements for transcription", "Apply to disease"],
          slides: [
              { t: "RNA polymerases: division", d: "Pol I (rRNA), Pol II (mRNA, snRNA, sensitive to α-amanitin), Pol III (tRNA, 5S rRNA). Bacterial RNA pol holoenzyme (α₂ββ'σ) recognizes promoters."},
              { t: "Transcription in bacteria", d: "σ factor binds -10/-35 boxes. Initiation, elongation, termination (ρ-dependent/independent). RNA synthesized 5'→3' without primer."},
              { t: "Eukaryotic transcription & general TFs", d: "TFIID (TBP) binds TATA box, recruits Pol II + TFIIB/F/E/H. Mediator complex integrates regulatory signals."},
              { t: "Epigenetic control", d: "Chromatin remodeling, histone acetylation/methylation influence transcription. Aberrant transcription linked to cancer & developmental disorders."}
          ] },
        { num: "08", title: "Translation", outcomes: ["Protein synthesis steps", "Genetic code", "Mutations in disease"],
          slides: [
              { t: "Translation machinery", d: "Ribosome (rRNA + proteins), aminoacyl-tRNAs, mRNA, soluble factors. Initiation: AUG start codon (Kozak in eukaryotes, Shine-Dalgarno in bacteria)."},
              { t: "Genetic code features", d: "Triplet codons, degenerate, non-overlapping, universal. Start AUG (Met), stop codons (UAA, UAG, UGA). tRNA anticodon pairs."},
              { t: "Mutations impact", d: "Missense (different amino acid), nonsense (premature stop), frameshift (insertion/deletion). Altered proteins cause diseases like sickle cell, cystic fibrosis."},
              { t: "Eukaryotic vs prokaryotic translation", d: "Eukaryotic mRNAs are monocistronic, cap-dependent scanning. Prokaryotes: polycistronic, Shine-Dalgarno sequence."}
          ] },
        { num: "09", title: "RNA Splicing", outcomes: ["Explain RNA splicing", "Mature mRNA structure", "Significance of splicing"],
          slides: [
              { t: "5' capping and polyadenylation", d: "m⁷G cap added at 5' end protects from exonucleases & enhances translation. Poly(A) tail (200 A's) added at 3' end for stability & export."},
              { t: "Intron/exon splicing mechanism", d: "Spliceosome (snRNPs U1,U2,U4,U5,U6) recognizes 5' splice site, branch point, 3' site. Two transesterification reactions remove intron as lariat."},
              { t: "Alternative splicing & ribozymes", d: "Alternative splicing generates protein diversity from one gene. Self-splicing introns (group I/II) are catalytic RNAs (ribozymes)."},
              { t: "Clinical significance", d: "Splicing defects cause β-thalassemia, spinal muscular atrophy. Mature mRNA contains only exons + UTRs."}
          ] },
        { num: "10", title: "Gene Cloning", outcomes: ["Process of gene cloning", "Southern/Northern blotting", "DNA libraries"],
          slides: [
              { t: "Molecular cloning basics", d: "Insert DNA fragment into vector (plasmid, phage) → transform host (E. coli) → select via antibiotic resistance → amplify recombinant DNA."},
              { t: "Genomic vs cDNA libraries", d: "Genomic library includes introns/promoters; cDNA derived from reverse-transcribed mRNA, lacks introns, reflects expressed genes only."},
              { t: "Southern blot", d: "Digest DNA, gel electrophoresis, transfer to membrane, hybridize with labeled probe → detect specific sequences, RFLPs, gene rearrangements."},
              { t: "Northern blot", d: "Similar but for RNA → detect gene expression levels, transcript size. Useful for cancer diagnostics & splicing defects."}
          ] },
        { num: "11", title: "Recombinant DNA Technology", outcomes: ["DNA sequencing methods", "Blotting/hybridization", "Cloning applications"],
          slides: [
              { t: "Sanger (dideoxy) sequencing", d: "ddNTPs terminate DNA synthesis at specific bases; four reactions separate by gel → read sequence from autoradiogram. Maxam-Gilbert chemical method."},
              { t: "Restriction endonucleases", d: "Cut DNA at palindromic sequences (4–8 bp), produce sticky/blunt ends. Use DNA ligase to join fragments."},
              { t: "Knockout mice & transgenics", d: "Homologous recombination in ES cells disrupts target gene (neomycin resistance + tk selection). Creates animal models of human diseases."},
              { t: "Expression vectors & protein production", d: "Cloned cDNA under strong promoter (lac, T7) → recombinant protein (e.g., G-CSF, insulin) in bacteria or mammalian cells."}
          ] },
        { num: "12", title: "Polymerase Chain Reaction (PCR)", outcomes: ["Explain PCR vs other amplification", "Forensic/clinical uses", "Steps of PCR"],
          slides: [
              { t: "PCR principles & cycles", d: "Denature (94°C) → anneal primers (~55°C) → extend (72°C, Taq polymerase). 20–40 cycles yield exponential amplification (2ⁿ copies)."},
              { t: "Clinical & forensic utility", d: "Detect HIV, SARS-CoV-2, minimal residual disease in leukemia, genetic mutations, crime scene DNA (fingerprint, saliva). Prenatal diagnosis."},
              { t: "Key steps in detail", d: "Initial denaturation 5 min, then cycles of heating/annealing/extension. Final hold. Fast, sensitive, replaces Southern blot for many assays."},
              { t: "PCR applications in medicine", d: "Carrier screening, paternity testing, twin zygosity, transplant engraftment, tumor mutation analysis and preimplantation genetic diagnosis."}
          ] }
    ];

    function buildHTML() {
        const container = document.getElementById('sessionsGrid');
        let html = '';
        sessionsData.forEach(sess => {
            // build outcomes block
            let outcomesHtml = `<div class="learning-targets"><strong>🎯 Learning outcomes:</strong><ul style="margin-top:6px; margin-left:20px;">`;
            sess.outcomes.forEach(out => {
                outcomesHtml += `<li>${out}</li>`;
            });
            outcomesHtml += `</ul></div>`;
            let slidesHtml = `<div style="margin-top:6px;"><strong>📑 Slide-by-slide explanations:</strong></div>`;
            sess.slides.forEach(slide => {
                slidesHtml += `
                    <div class="slide-summary">
                        <div class="slide-title">📌 ${slide.t}</div>
                        <div class="slide-desc">${slide.d}</div>
                    </div>
                `;
            });
            const sessionContent = outcomesHtml + slidesHtml;
            html += `
                <div class="session-card" data-session="${sess.num}">
                    <div class="session-header" onclick="toggleSession(this)">
                        <div style="display: flex; align-items: center; gap: 0.7rem; flex-wrap: wrap;">
                            <span class="session-number">Session ${sess.num}</span>
                            <span class="session-title">${sess.title}</span>
                        </div>
                        <span class="toggle-icon">▼</span>
                    </div>
                    <div class="session-content">
                        ${sessionContent}
                    </div>
                </div>
            `;
        });
        container.innerHTML = html;
    }

    window.toggleSession = function(headerElem) {
        const contentDiv = headerElem.parentElement.querySelector('.session-content');
        const icon = headerElem.querySelector('.toggle-icon');
        if (contentDiv.classList.contains('open')) {
            contentDiv.classList.remove('open');
            icon.innerHTML = '▼';
        } else {
            contentDiv.classList.add('open');
            icon.innerHTML = '▲';
        }
    };

    buildHTML();

    // ensure first session open for visibility? optional
    window.addEventListener('DOMContentLoaded', () => {
        const firstSessionContent = document.querySelector('.session-card .session-content');
        if (firstSessionContent) {
            firstSessionContent.classList.add('open');
            const firstIcon = document.querySelector('.session-card .toggle-icon');
            if (firstIcon) firstIcon.innerHTML = '▲';
        }
    });
</script>
</body>
</html>
```
