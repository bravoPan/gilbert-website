---
title: "Transloc: transparent indoor localization with uncertain human participation for instant delivery"
authors:
- Yu Yang
- Yi Ding
- admin
- Guang Wnag
- Xiaoyang Xie
- Tian He
- Desheng Zhang
date: "2020-09-21T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2020-09-21T00:00:00Z"

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;
# 7 = Thesis; 8 = Patent
publication_types: ["1"]

# Publication name and optional abbreviated publication name.
publication: In *MobiCom 20 Proceedings of the 26th Annual International Conference on Mobile Computing and Networking*
publication_short: In *MobiCom20*

abstract: Instant delivery is an important urban service in recent years because of the increasing demand. An important issue for delivery platforms is to keep updating the status of couriers especially the real-time locations, which is challenging when they are in an indoor environment. We argue the previous indoor localization techniques cannot be applied in the instant delivery scenario because they require extra deployed infrastructures and extensive labor work. In this work, we perform the couriers' indoor localization transparently in a predictive manner without extra actions of couriers by existing data from the platform including order progress reports and couriers' trajectories. Specifically, we present TransLoc to predict couriers' indoor locations by addressing two challenges including uncertain reporting behaviors and uncertain indoor mobility behaviors. Our key idea lies in two insights (i) couriers' behaviors are consistent in indoor/outdoor environments; (ii) localization, as a spatial inference problem, could be converted to a temporal inference problem. We evaluate TransLoc on 565 couriers from an instant delivery company, which improves baselines by at most 72%, and achieves a competitive result compared to a label-extensive approach. As a case study, we apply TransLoc to optimize the order dispatching strategy, which reduces the delivery time by 24%.


# Summary. An optional shortened abstract.
summary: In this work, we perform the first study on couriers’ reporting behaviors and indoor mobility for instant delivery services. We found most of their indoor/outdoor reporting behaviors are consistent, which motivates us to use machine learning models to correct their indoor reporting behaviors by the outdoor reporting model. Further, we design a symbolic mobility graph, which captures their indoor mobility without prior knowledge of the indoor environment. Based on the experiment results, our system can improve the localization accuracy by 64% and 72% compared with the Wi-Fi GPS-based method and competitive accuracy with the fingerprinting-based method. With a case study, our system helps the delivery platform reduce the courier redundant time by 24%;

tags:
- Source Themes
featured: false

links:
- name: ACM
  url: https://dl.acm.org/doi/10.1145/3372224.3419198
url_source: https://dl.acm.org/doi/pdf/10.1145/3372224.3419198?casa_token=jB1SAZECoFwAAAAA:h7-oUFSPzJZDij1THEfRGcIZFUiWLhLoD9_yzYHAn1ybNZ16YjXmVJCx-fgMeQ_-X_0JJDCaHFaU9Q


# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.


# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects:
- internal-project

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: example
---
