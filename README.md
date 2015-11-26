
## google-scholar-crawler

#### You can start the crawler with a start_url:

```
cd googlescholar
scrapy crawl googlescholar -a start_url="https://scholar.google.com/scholar?hl=en&q=estimate+ctr&btnG=&as_sdt=1%2C5&as_sdtp="
```

#### Core code, super easy, isn't it?

```
    list_css_rules = {
        '.gs_r': {
            'title': '.gs_rt a *::text',
            'url': '.gs_rt a::attr(href)',
            'related-text': '.gs_ggsS::text',
            'related-type': '.gs_ggsS .gs_ctg2::text',
            'related-url': '.gs_ggs a::attr(href)',
            'citation-text': '.gs_fl > a:nth-child(1)::text',
            'citation-url': '.gs_fl > a:nth-child(1)::attr(href)',
            'authors': '.gs_a a::text',
            'description': '.gs_rs *::text',
            'journal-year-src': '.gs_a::text',
        }
    }

    def parse_1(self, response):
        info('Parse '+response.url)
        x = self.parse_with_rules(response, self.list_css_rules, dict)
        pp.pprint(x[0]['.gs_r'])
```

#### Example results

```
[{'authors': '',
  'citation-text': u'Related articles',
  'citation-url': u'/scholar?q=related:DdunAWA0VAQJ:scholar.google.com/&hl=en&as_sdt=0,5',
  'description': u'...  sup 94/Nb(n,. gamma. )/sup 95/Nb, /sup 95m/Nb reaction for the  CTR  reactor technology  ...  Therefore  an important and timely cross section need is an  estimate  and measurement of the /sup  94/Nb(n,..gamma..)/sup 95/Nb, /sup 95m/Nb reaction in the keV-MeV energy region.  ...',
  'journal-year-src': u'PJ Persiani, EM Pennington, YD Harker\u2026 - Natl. Bur. Stand.(US), \u2026, 1975 - osti.gov',
  'related-text': '',
  'related-type': '',
  'related-url': '',
  'title': u'/sup 94/Nb (n,. gamma.)/sup 95/Nb,/sup 95m/Nb reaction for the  CTR  reactor technology program',
  'url': u'http://www.osti.gov/scitech/biblio/7362256'},
 {'authors': '',
  'citation-text': u'Cited by 315',
  'citation-url': u'/scholar?cites=14514417774733894833&as_sdt=2005&sciodt=0,5&hl=en',
  'description': u"...  that ESPRIT exploits the invariance property of both the transmit array and the receive array in  a bistatic MIMO radar to  estimate  the target's  ...  multiple sources, we must determine which  eigenvalue of Ct corresponds to which eigenvalue of Cr for the same target [5]. Let  Ctr  be the  ...",
  'journal-year-src': u'C Duofang, C Baixiao, Q Guodong - Electronics Letters, 2008 - IET',
  'related-text': '',
  'related-type': '',
  'related-url': '',
  'title': u'Angle estimation using ESPRIT in MIMO radar',
  'url': u'http://digital-library.theiet.org/content/journals/10.1049/el_20080276'},
 {'authors': '',
  'citation-text': u'Cited by 285',
  'citation-url': u'/scholar?cites=14176183672650641407&as_sdt=2005&sciodt=0,5&hl=en',
  'description': u"...  In contrast to the ~- 7r ouh mode we cannot  estimate  the decay rate for the 7rTr~rv h mode in  a clean manner  ...  coupling constant for the axial current to create A 1. As for the' absolute magnitude  we can take advantage of Weinberg's result [6] 2 2 2 2 2 rnA/f A ~ mp/fp -  cTr  ~ (m2/2f  ...",
  'journal-year-src': u'HB Thacker, JJ Sakurai - Physics Letters B, 1971 - Elsevier',
  'related-text': '',
  'related-type': '',
  'related-url': '',
  'title': u'Lifetimes and branching ratios of heavy leptons',
  'url': u'http://www.sciencedirect.com/science/article/pii/0370269371901195'},
 {'authors': '',
  'citation-text': u'Cited by 85',
  'citation-url': u'/scholar?cites=1077886289905774040&as_sdt=2005&sciodt=0,5&hl=en',
  'description': u'...  Please note that terms and conditions apply. Parametric processes in magnetically confined CTR  plasmas  ...  Page 2. NUCLEAR FUSION 18 3 (1978) REVIEW PAPER PARAMETRIC  PROCESSES IN MAGNETICALLY CONFINED  CTR  PLASMAS  ...',
  'journal-year-src': u'M Porkolab - Nuclear fusion, 1978 - iopscience.iop.org',
  'related-text': '',
  'related-type': '',
  'related-url': '',
  'title': u'Parametric processes in magnetically confined  CTR  plasmas',
  'url': u'http://iopscience.iop.org/0029-5515/18/3/008'},
 {'authors': u'Y Hashidoko',
  'citation-text': u'Cite',
  'citation-url': u'#',
  'description': u'...  rumen degradability (aNDF in stalks and starch in kernels) and in vitro gas production of kernels  from three corn hybrids treated (TT) or not treated (control,  CTR ) with insecticides  ...  article. Evaluation  of indirect methods to  estimate  the nutritional value of tropical feeds for ruminants.  ...',
  'journal-year-src': u'T Hiura,  , Y Kobayashi\u2026 - Animal Feed Science and \u2026, 2010 - infona.pl',
  'related-text': '',
  'related-type': '',
  'related-url': '',
  'title': u'\u2026 (aNDF in stalks and starch in kernels) and in vitro gas production of kernels from three corn hybrids treated (TT) or not treated (control,  CTR ) with insecticides against \u2026',
  'url': u'https://www.infona.pl/resource/bwmeta1.element.elsevier-cf0eeacf-3c1f-355d-bb25-cfc9decc3625'},
 {'authors': '',
  'citation-text': u'Cited by 328',
  'citation-url': u'/scholar?cites=12940939836868274762&as_sdt=2005&sciodt=0,5&hl=en',
  'description': u'...  protein NeuN or the astrocytic marker S100\u03b2 did not differ between Enr-129 and  Ctr -129 mice,  but the percentage of BrdU + cells that did not express NeuN or S100\u03b2 was significantly lower  in Enr-129 than in  Ctr -129 mice ( Figure 1b; p = 0.0247). To  estimate  the absolute  ...',
  'journal-year-src': u'G Kempermann, EP Brandon, FH Gage - Current Biology, 1998 - Elsevier',
  'related-text': u'sciencedirect.com ',
  'related-type': u'[HTML]',
  'related-url': u'http://www.sciencedirect.com/science/article/pii/S0960982207003776',
  'title': u'Environmental stimulation of 129/SvJ mice causes increased cell proliferation and neurogenesis in the adult dentate gyrus',
  'url': u'http://www.sciencedirect.com/science/article/pii/S0960982207003776'},
 {'authors': u'DH Brooks',
  'citation-text': u'Cited by 19',
  'citation-url': u'/scholar?cites=5643306643529251632&as_sdt=2005&sciodt=0,5&hl=en',
  'description': u'...  In contrast to  CtR  methods, RtC methods first explicitly  estimate  the unsampled  k-space data in each coil, and then form an image by combining the measured and  estimated k-space data. The  estimate  is based on a model that  ...',
  'journal-year-src': u'WS Hoge,   - Magnetic Resonance in Medicine, 2008 - Wiley Online Library',
  'related-text': u'nih.gov ',
  'related-type': u'[HTML]',
  'related-url': u'http://www.ncbi.nlm.nih.gov/pmc/articles/PMC3984006/',
  'title': u'Using GRAPPA to improve autocalibrated coil sensitivity estimation for the SENSE family of parallel imaging reconstruction algorithms',
  'url': u'http://onlinelibrary.wiley.com/doi/10.1002/mrm.21634/full'},
 {'authors': '',
  'citation-text': u'Cited by 33',
  'citation-url': u'/scholar?cites=14751716916583277517&as_sdt=2005&sciodt=0,5&hl=en',
  'description': u'...  1995). Initial values of parameters  ctr  and Pr were 68.50 and 1.5 for males and 55.13  and 1.5 for females.  ...  Page 119. Zheng et al.: A length-based approach to  estimate  population abundance of Tanner crab in Bristol Bay, Alaska Fig.  ...',
  'journal-year-src': u'J Zheng, GH Kruse, MC Murphy - \u2026 SPECIAL PUBLICATION OF \u2026, 1998 - books.google.com',
  'related-text': '',
  'related-type': '',
  'related-url': '',
  'title': u'A length-based approach to  estimate  population abundance of Tanner crab, Chionoecetes bairdi, in Bristol Bay, Alaska',
  'url': u'https://books.google.com/books?hl=en&lr=&id=WnNVQKNwRsQC&oi=fnd&pg=PA97&dq=estimate+ctr&ots=wvAOjWC4xW&sig=0k4o4uBv2xTsVJCjJBosZcPcOs4'},
 {'authors': u'M Weynants M Javaux',
  'citation-text': u'Cited by 108',
  'citation-url': u'/scholar?cites=15734101908307055675&as_sdt=2005&sciodt=0,5&hl=en',
  'description': u'...  Using Pedotransfer Functions to  Estimate  the van Genuchten\u2013Mualem Soil Hydraulic Properties:  A Review.  ...  Nemes et al. (2006a,b) applied a nearest neighbor method to  estimate  the water  retention at 330 and 15,000 cm using a hierarchical set of predictor variables.  ...',
  'journal-year-src': u'H Vereecken,  ,  \u2026 - \u2026, 2010 - dl.sciencesocieties.org',
  'related-text': u'researchgate.net ',
  'related-type': u'[PDF]',
  'related-url': u'http://www.researchgate.net/profile/Mathieu_Javaux/publication/234168627_Using_Pedotransfer_Functions_to_Estimate_the_van_Genuchten_Mualem_Soil_Hydraulic_Properties_A_Review/links/0fcfd507d93d0129cd000000.pdf',
  'title': u'Using pedotransfer functions to  estimate  the van Genuchten\u2013Mualem soil hydraulic properties: A review',
  'url': u'https://dl.sciencesocieties.org/publications/vzj/abstracts/9/4/795'},
 {'authors': u'L Li W Chu J Langford',
  'citation-text': u'Cited by 353',
  'citation-url': u'/scholar?cites=9425096206449071896&as_sdt=2005&sciodt=0,5&hl=en',
  'description': u"...  By doing so, a bandit algorithm can generalize  CTR  information from one article/user to another,  and learn to choose good articles more  ...  However, obtaining infor- mation about the arms' average  payoffs (ie, exploration) can re- fine A's  estimate  of the arms' payoffs and in turn  ...",
  'journal-year-src': u',  ,  , RE Schapire - Proceedings of the 19th \u2026, 2010 - dl.acm.org',
  'related-text': u'arxiv.org ',
  'related-type': u'[PDF]',
  'related-url': u'http://arxiv.org/pdf/1003.0146',
  'title': u'A contextual-bandit approach to personalized news article recommendation',
  'url': u'http://dl.acm.org/citation.cfm?id=1772758'}]
```
