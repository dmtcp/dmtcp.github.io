---
title: Publications
nav_order: 8
---

::: cell
## Citing DMTCP (please cite this publication):

- [DMTCP: Transparent Checkpointing for Cluster Computations and the
  Desktop](papers/dmtcp.pdf).\
  Jason Ansel, Kapil Arya and Gene Cooperman.\
  *23rd IEEE International Parallel and Distributed Processing Symposium
  (IPDPS\'09)*.\
  12 pages, Rome, Italy. May, 2009.\
  • [Slides](papers/dmtcp-slides-ipdps09.pdf).\
  • [Bibtex](papers/dmtcp.bib).

------------------------------------------------------------------------

A.  [DMTCP Publications (enhancements to the DMTCP
    distribution)](publications.html#enhancements)
B.  [Publications and Conference Presentations *using* DMTCP in their
    work](publications.html#others)

------------------------------------------------------------------------

## [A. DMTCP Publications]{#enhancements} (an annotated history of enhancements to the DMTCP distribution; reverse chronological order):

- [Enabling Practical Transparent Checkpointing for {MPI}: A Topological
  Sort
  Approach](http://www.ccs.neu.edu/home/gene/papers/cluster24.pdf),\
  (and earlier technical report of same name at
  <https://arxiv.org/abs/2408.02218>)\
  Yao Xu and Gene Cooperman,\
  *Proc. of 2024 IEEE International Conference on Cluster Computing
  (Cluster\'24)*, Sept., 2024, IEEE Computer Society,\
  [Bibtex](papers/cluster24.bib.html).\
  *(The MANA paper introduced \"split processes\" to transparently
  checkpointing independently of the underlying network software. But
  that algorithm interposed an MPI barrier in front of each collective
  communication, in order to ensure a safe syncronization point (and
  hence a consistent snapshot for checkpointing). This incurred high
  runtime overhead for collective communication. A new sequence number
  algorithm is shown with zero additional inter-process communication,
  and so has almost no runtime overhead.)*

- [CRAC: Checkpoint-Restart Architecture for CUDA with Streams and
  UVM](http://www.ccs.neu.edu/home/gene/papers/sc20.pdf),\
  (and earlier technical report of same name at
  <https://arxiv.org/abs/2008.10596>)\
  Twinkle Jain and Gene Cooperman,\
  *Proc. of the Int. Conf. for High Performance Computing, Networking,
  Storage and Analysis (SC\'20)*, pp. 1083\--1097, Nov., 2020, IEEE
  Computer Society,\
  [Bibtex](papers/sc20.bib.html).\
  *(Extending \"split-process\" approach to efficient checkpointing for
  CUDA: This typically involves less than 1% runtime overhead, unlike
  the earlier approach of CRUM, which required a separate proxy
  process.)*

- [MANA for MPI: MPI-Agnostic Network-Agnostic Transparent
  Checkpointing](http://www.ccs.neu.edu/home/gene/papers/hpdc19.pdf),\
  Rohan Garg, Gregory Price, and Gene Cooperman, *Proc. of 28th Int.
  Symp. on High Performance Parallel and Distributed Computing
  (HPDC\'19)*,\
  Phoenix, AZ, USA, ACM, pp. 49\--60, June, 2019, (and tech. report at
  <https://arxiv.org/abs/1904.12595>),\
  • [Slides (pdf)](papers/hpdc19-slides.pdf), [Slides
  (odp)](papers/hpdc19-slides.odp), [Slides
  (pptx)](papers/hpdc19-slides.pptx). [Bibtex](papers/hpdc19.bib).\
  *(Novel \"split-process\" approach to isolating and checkpointing just
  the MPI application at the original cluster: On restart (on the same
  cluster or on a different one), the underlying network, the
  ranks-per-node, and even the MPI library (e.g., MPICH or Open MPI) can
  each be changed.)*

- [CRUM: Checkpoint-Restart Support for CUDA\'s Unified
  Memory](http://www.ccs.neu.edu/home/gene/papers/cluster18.pdf),\
  Rohan Garg, Apoorve Mohan, Michael Sullivan, and Gene Cooperman,
  *Proc. of IEEE Int. Conf. on Cluster Computing (Cluster\'18)*,\
  Belfast, United Kingdon, IEEE, pp. 302\--313, Sept., 2018, (and tech.
  report at <https://arxiv.org/abs/1808.00117>),
  [Bibtex](papers/cluster18.bib.html).\
  *(Transparent checkpointing of CUDA, including UVM (Unified Virtual
  Memory), using a proxy approach)*

- [System-level Scalable Checkpoint-Restart for Petascale
  Computing](http://www.ccs.neu.edu/home/gene/papers/icpads16.pdf).\
  Jiajun Cao, Kapil Arya, Rohan Garg, Shawn Matott, Dhabaleswar K.
  Panda, Hari Subramoni, Jérôme Vienne and Gene Cooperman,\
  *Proc. of 22nd IEEE Int. Conf. on Parallel and Distributed Systems
  (ICPADS\'16)*,\
  Wuhan, China, IEEE Press, pp. 932\--941, Dec., 2016,
  [Bibtex](papers/icpads16.bib.html).\
  *(Scalable transparent checkpointing: MPI-based HPCG using 32,752 CPU
  cores, and MPI-based NAMD using 16,368 CPU cores)*

- [Design and Implementation for Checkpointing of Distributed Resources
  using Process-level Virtualization](papers/cluster16.pdf).\
  Kapil Arya, Rohan Garg, Artem Y. Polyakov and Gene Cooperman,\
  *Proc. of IEEE Int. Conf. on Cluster Computing (Cluster\'16)*,\
  pp. 402\--412, Taipei, Taiwan, IEEE Press, Sept., 2016.
  [Bibtex](papers/cluster16a.bib.html).\
  *(Extensible, adaptable, transparent checkpointing via a plugin
  implementation of process virtualization)*

- [Transparent Checkpoint-Restart over
  InfiniBand](http://www.ccs.neu.edu/home/gene/papers/hpdc14.pdf).\
  Jiajun Cao, Gregory Kerr, Kapil Arya and Gene Cooperman,\
  *Proc. of ACM Symposium on High Performance Parallel and Distributed
  Computing (HPDC\'14)*,\
  12 pages, Vancouver, Canada, June, 2014.
  [Bibtex](papers/hpdc14.bib.html).\
  *(Transparent checkpointing of MPI over InfiniBand; no need to tear
  down network, and reconstruct during restart)*

- [Checkpoint-Restart for a Network of Virtual
  Machines](http://www.ccs.neu.edu/home/gene/papers/cluster13.pdf).\
  Rohan Garg, Komal Sodha, Zhengping Jin and Gene Cooperman,\
  *Proc. of 2013 IEEE Computer Society International Conference on
  Cluster Computing*.\
  8 pages, Indianapolis, USA. Sept., 2013.
  [Slides](papers/ckpt-vm-cluster13-slides.pdf).
  [Bibtex](papers/ckpt-vm-cluster13.bib.html).\
  *(Transparent checkpointing of network of Qemu\'s over KVM)*

- [DMTCP: Transparent Checkpointing for Cluster Computations and the
  Desktop](papers/dmtcp.pdf).\
  Jason Ansel, Kapil Arya and Gene Cooperman.\
  *Proc. of 23rd IEEE International Parallel and Distributed Processing
  Symposium (IPDPS\'09)*.\
  12 pages, Rome, Italy. May, 2009.
  [Slides](papers/dmtcp-slides-ipdps09.pdf).
  [Bibtex](papers/dmtcp.bib).\
  *(Transparent checkpointing of distributed processes)*

- [Transparent Adaptive Library-Based Checkpointing for Master-Worker
  Style
  Parallelism](http://www.ccs.neu.edu/home/gene/papers/ccgrid06.pdf),\
  Gene Cooperman, Jason Ansel and Xiaoqin Ma,\
  *Proc. of 6th IEEE Int. Symp. on Cluster Computing and the Grid
  (CCGrid06)*,\
  pp. 283\--291, IEEE Press, 2006 [Bibtex](papers/ccgrid06.bib)\
  *(Master-worker style checkpointing experiment in distributed
  checkpointing, prior to DMTCP itself)*

- [Transparent User-Level Checkpointing for the Native POSIX Thread
  Library for Linux](papers/mtcp.pdf).\
  Michael Rieker, Jason Ansel, and Gene Cooperman.\
  *Proc. of 2006 International Conference on Parallel and Distributed
  Processing Techniques and Applications (PDPTA\'06)*.\
  pp. 492\--498, Las Vegas, NV. Jun., CSREA Press, 2006.
  [Bibtex](papers/mtcp.bib).\
  *(The original MTCP: Transparent checkpointing for multi-threaded
  checkpointing for a single process)*

------------------------------------------------------------------------

## [B. Publications and Conference Presentations mostly by other teams, and *using* DMTCP in their work]{#others} (not simply citing DMTCP) *(in reverse chronological order)*:

1.  [Live Migration of Multi-Container Kubernetes Pods in Multi-Cluster
    Serverless Edge
    Systems](https://dl.acm.org/doi/abs/10.1145/3660319.3660330),\
    Poggiani, Leonardo and Puliafito, Carlo and Virdis, Antonio and
    Mingozzi, Enzo,\
    *Proceedings of the 1st Workshop on Serverless at the Edge
    (SEATED\'24)* pp. 9\--16, Sept., 2024,\
    [Bibtex](papers/seated24.bib)

2.  [AdapCK: Optimizing I/O for Checkpointing on Large-Scale High
    Performance Computing
    Systems](https://link.springer.com/chapter/10.1007/978-3-031-69583-4_24),\
    Jia, Jie and Liu, Yi and Liu, Yanke and Chen, Yifan and Lin, Fang,\
    *European Conference on Parallel Processing (Euro-Par\'24)* Lecture
    Notes in Computer Science **14803**, pp. 342\--355, Aug., 2024,
    Springer Nature,\
    [Bibtex](papers/ecpp24.bib.html)

3.  [Optimizing Checkpoint-Restart Mechanisms for HPC with DMTCP in
    Containers at NERSC](https://arxiv.org/abs/2407.19117),\
    Timalsina, Madan and Gerhardt, Lisa and Tyler, Nicholas and
    Blaschke, Johannes P and Arndt, William,\
    *arXiv preprint arXiv:2407.19117*, 9 pages, Jul., 2024,\
    [Bibtex](papers/arxiv24.bib.html)

4.  [Limitless FaaS: Overcoming serverless Functions Execution Time
    Limits with Invoke Driven Architecture and Memory
    Checkpoints](https://ieeexplore.ieee.org/abstract/document/10533362?casa_token=4jp1iSXhY5gAAAAA:JTK1iXGcudt7wg-Pr2Kvb--u71QNi2cFHZnUkEnhGTiKfYkVdTdv5etfMM48PKCz_rIz9Go8Zg),\
    Rodrigo Landa Andraca and Mahdi Zaree,\
    *10th International Conference on Web Research (ICWR\'24)*,
    pp. 210\--215, May, 2024,\
    [Bibtex](papers/icwr24.bib.html)

5.  [*Application-Transparent Strategies to Optimize Limited Resources
    in HPC and Big Data*](https://www.proquest.com/docview/3039622274),\
    Twinkle Jain, PhD thesis, Northeastern University, May, 2024,\
    [Bibtex](papers/jainthesis24.bib.html)

6.  [DCU-CHK: Checkpointing for Large-scale CPU-DCU Heterogeneous
    Computing
    Systems](https://link.springer.com/article/10.1007/s42514-023-00178-4),\
    Jia, Jie and Lin, Xinyuan and Lin, Fang and Liu, Yi,\
    *CCF Transactions on High Performance Computing* pp. 171\--187,
    Jan., 2024, Springer,\
    [Bibtex](papers/ccf24.bib.html)

7.  [Digital Twin Migration using the {OKD} Platform: A Use-Case for
    Emergency
    Vehicles](https://ieeexplore.ieee.org/abstract/document/10368494),\
    Ribeiro, Bruno and Gonçalves, Pedro and Bartolomeu, Paulo C,\
    *33rd International Telecommunication Networks and Applications
    Conference (ATNAC\'24)*, pp. 63\--69, Dec.., 2023, IEEE,\
    [Bibtex](papers/atnac23.bib).

8.  [HPC@Cloud: a Provider-Agnostic Toolkit to Enable the Execution of
    {HPC} Applications on Public
    Clouds](https://repositorio.ufsc.br/handle/123456789/254816),\
    Pereira Filho, Vanderlei Munhoz,\
    *Masters Thesis, Universidade Federal de Santa Catarina*,
    Nov. 4, 2023,\
    [Bibtex](papers/pereira23.bib.html).

9.  [Implementation-Oblivious Transparent Checkpoint-Restart for
    MPI](https://dl.acm.org/doi/abs/10.1145/3624062.3624255),\
    Xu, Yao and Belyaev, Leonid and Jain, Twinkle and Schafer, Derek and
    Skjellum, Anthony and Cooperman, Gene,\
    *Proceedings of the SC\'23 Workshops of The International Conference
    on High Performance Computing, Network, Storage, and Analysis
    (SC-W\'23; SuperCheck\'23)*, pp. 1738\--1747, Nov., 2023,\
    [Bibtex](papers/supercheck23.bib.html)

10. [Migration Transparente de
    Conteneurs](https://www.researchgate.net/profile/Abdelaziz-Hamdi-2/publication/374256675_ZFS-volume-migrator_Un_outil_de_migration_de_conteneurs_de_niveau_de_stockage_pour_les_clusters_Kubernetes_bases_sur_zfs/links/651593f92c6cfe2cc215bbb0/ZFS-volume-migrator-Un-outil-de-migration-de-conteneurs-de-niveau-de-stockage-pour-les-clusters-Kubernetes-bases-sur-zfs.pdf),\
    Hamdi Abdelaziz, Daniele Miorandi, and Guillaume Pierre,\
    *Masters Thesis*, École nationale Supérieurede lInformatique; ex.
    INI (Institut National de formation en Informatique, Alger,
    Alg&eactue;rie), Sept., 2023,\
    [Bibtex](papers/abdelazizthesis23.bib.html)

11. [*Gestión del Almacenamiento para Tolerancia a Fallos en Computación
    de Altas Prestaciones*](https://ddd.uab.cat/record/287110),\
    Betzabeth León, PhD thesis, Universitat Autónoma de Barcelona, Mar.,
    2023,\
    [Bibtex](papers/leonthesis23.bib.html)

12. [Debugging MPI Implementations via
    Reduction-to-Primitives](https://ieeexplore.ieee.org/abstract/document/10025545),\
    Cooperman, Gene and Li, Dahong and Zhao, Zhengji,\
    *IEEE/ACM Third International Symposium on Checkpointing for
    Supercomputing (SuperCheck\'22*, pp. 10\--18, Nov., 2022,\
    [Bibtex](papers/supercheck22.bib.html)

13. [Good Shepherds Care For Their Cattle: Seamless Pod Migration in
    Geo-Distributed
    Kubernetes](https://hal.inria.fr/hal-03587358/document),\
    Paulo Souza Junior, Daniele Miorandi, and Guillaume Pierre,\
    *6th IEEE Int. Conf. on Fog and Edge Computing (ICFEC\'22)*,
    9\~pages, May, 2022,\
    [Bibtex](papers/icfec22.bib.html)

14. [A Model of Checkpoint Behavior for Applications that have
    I/O](https://link.springer.com/article/10.1007/s11227-022-04482-8),\
    León, Betzabeth and M{éndez, Sandra and Franco, Daniel and Rexachs,
    Dolores and Luque, Emilio,\
    *The Journal of Supercomputing* **78**, pp.  15404--15436, Apr.,
    2022, Springer,\
    [Bibtex](papers/jsc22.bib.html)
    [Bibtex](papers/leonthesis23.bib.html)

15. [*Provisioning Strategies for Centralized Bare-Metal
    Clusters*](http://hdl.handle.net/2047/D20420684),\
    Apoorve Mohan, PhD thesis, Northeastern University, Dec., 2021,\
    [Bibtex](papers/mohanthesis21.bib.html)

16. [MANA-2.0: A Future-Proof Design for Transparent Checkpointing of
    MPI at Scale](https://arxiv.org/abs/2112.05858),\
    Yao Xu, Zhengji Zhao, Rohan Garg, Harsh Khetawat, Rebecca
    Hartman-Baker, Gene Cooperman,\
    *Int. Symp. on Checkpointing for Supercomputing (SuperCheck\'SC-21)*
    , (SC Workshops Supplementaray Proceedings (SCWS)) pp. 68\--78,
    Nov., 2021,\
    [Bibtex](papers/sc21-scwp.bib.html)

17. [Assessing the Use Cases of Persistent Memory in High-Performance
    Scientific Computing](https://arxiv.org/pdf/2109.02166.pdf),\
    Yehonatan Fridman, Yaniv Snir, Matan Rusanovsky, Kfir Zvi, Harel
    Levin, Danny Hendler, Hagit Attiya, and Gal Oren,\
    *2021 IEEE/ACM 11th Workshop on Fault Tolerance for HPC at eXtreme
    Scale (FTXS); workshop at SC21*, pp. 11\--20, IEEE, Oct., 2021\
    [Bibtex](papers/sc21-ftxs.bib)

18. [Service Migration in a Distributed Virtualization
    System](http://sedici.unlp.edu.ar/bitstream/handle/10915/128417/Documento_completo.pdf?sequence=1),\
    Pablo Andrés Pessolani, Luis Santiago Re, Tomás Andrés Fleitas,\
    *Journal of Computer Science \\& Technology* **21**(2),
    pp. 171\--187, Oct., 2021, Springer,\
    [Bibtex](papers/jcst21.bib.html)

19. [Performance and Energy Task Migration Model for Heterogeneous
    Clusters](https://link.springer.com/article/10.1007/s11227-021-03663-1),\
    Esteban Stafford and José Luis Bosque,\
    *The Journal of Supercomputing* **77**(9), pp. 10053\--10064, 2021,
    Springer,\
    [Bibtex](papers/jsc21b.bib.html)

20. [MigrOS: Transparent Live-Migration Support for Containerised RDMA
    Applications](https://www.usenix.org/system/files/atc21-planeta.pdf),\
    Maksym Planeta, Jan Bierbaum, Leo Sahaya Daphne Antony, Torsten
    Hoefler, and Hermann Härtig,\
    *2021 USENIX Annual Technical Conference (USENIX ATC 21)*,
    pp. 47\--63, July, 2021, (also as an [arXiv technical
    report](https://arxiv.org/abs/2009.06988) from Oct., 2020)\
    [Bibtex](papers/atc21.bib.html)

21. [Verifiable Application-level Checkpoint and Restart Framework for
    Parallel
    Computing](http://ceur-ws.org/Vol-3041/122-127-paper-22.pdf),\
    I. Gankevich and I. Petriakov and A. Gavrikov and D. Tereshchenko
    and G. Mozhaiskii,\
    *Proc. of 9th Int. Conf. on Distributed Computing and Grid
    Technologies in Science and Education (GRID\'2021)*, pp. 47\--63,
    July, 2021,\
    [Bibtex](papers/grid21.bib.html)

22. [An Innovative Approach for Cloud-Based Web Dev App
    Migration](https://link.springer.com/chapter/10.1007/978-981-16-4177-0_79),\
    C Sunil, KS Raghunandan, KN Ranjit, HK Chethan, and G Hemantha
    Kumar,\
    *ICT with Intelligent Applications*, pp. 807\--817, December, 2021,
    Springer\
    [Bibtex](papers/ict21.bib.html)

23. [Determination of Suitable Resource Discovery Tool and Methodology
    for High-Volume Internet of Things
    (IoT)](https://iopscience.iop.org/article/10.1088/1742-6596/1874/1/012046),\
    Mohd Tamizan Abu Bakar and Azrul Amri Jamal,\
    *Journal of Physics: Conference Series: 1st Int. Recent Trends in
    Engineering, Advanced Computing and Technology Conference
    (RETREAT)*, Volume 1874, Number 1, pp. 012046 (11 pages), June,
    2021, IOP Publishing,\
    [Bibtex](papers/retreat21.bib.html)

24. [ROS Rescue: Fault Tolerance System for Robot Operating
    System](https://link.springer.com/chapter/10.1007/978-3-030-45956-7_12),\
    Pushyami Kaveti and Hanumant Singh, Pushyami Kaveti and Hanumant
    Singh,\
    *Robot Operating System (ROS)*, pp. 381\--397, 2021, Springer, (and
    an [arXiv technical report](https://arxiv.org/abs/1910.01078) from
    Oct., 2019)\
    [Bibtex](papers/ros21.bib.html)

25. [Analysis of Parallel Application Checkpoint Storage for System
    Configuration](https://link.springer.com/article/10.1007/s11227-020-03445-1),\
    Betzabeth León, Daniel Franco, Dolores Rexachs, and Emilio Luque,\
    *The Journal of Supercomputing* **77**(5), pp. 4582\--4617, May,
    2021, Springer,\
    [Bibtex](papers/jsc21a.bib.html)

26. [Transparent Checkpointing for OpenGL Applications on
    GPUs](https://arxiv.org/abs/2103.04916),\
    David Hou and Jun Gan and Yue Li and Younes El Idrissi Yazami and
    Twinkle Jain,\
    *First Int. Symp. on Checkpointing for Supercomputing
    (SuperCheck21)*, 3 pages, Feb., 2021, (with [conf.
    program](https://supercheck.lbl.gov/resources),
    [slides](https://drive.google.com/file/d/1P5AB-WOuYS3KMThB_BjYe8JsuWdA3cUZ/view),
    and
    [video](https://drive.google.com/file/d/1GO2YMj_gVPrcnk3PWo70mF41yC3WDPCB/view))\
    [Bibtex](papers/supercheck21a.bib.html)

27. [Checkpointing SPAdes for Metagenome Assembly: Transparency versus
    Performance in Production](https://arxiv.org/abs/2103.03311),\
    Twinkle Jain and Jie Wang,\
    *First Int. Symp. on Checkpointing for Supercomputing
    (SuperCheck21)*, 4 pages, Feb., 2021, (with [conf.
    program](https://supercheck.lbl.gov/resources),
    [slides](https://drive.google.com/file/d/1PvIDb3KxPOcUvDxKyVy92HY-gtyQPvCZ/view),
    and
    [video](https://drive.google.com/file/d/1cmy_UMlZ15UMCMGU1m4VTeRWqwyCifw6/view))\
    [Bibtex](papers/supercheck21b.bib.html)

28. [Optimized Memoryless Fair-Share HPC Resources Scheduling Using
    Transparent Checkpoint-Restart
    Preemption](https://arxiv.org/abs/2102.12953),\
    Kfir Zvi and Gal Oren,\
    *First Int. Symp. on Checkpointing for Supercomputing
    (SuperCheck21)*, 4 pages, Feb., 2021, (with [conf.
    program](https://supercheck.lbl.gov/resources),
    [slides](https://drive.google.com/file/d/1Nh7hxkNpvWe1bxlXoIbwl2zOhWCWmdng/view),
    and
    [video](https://drive.google.com/file/d/1qU7HpRpWQbK86WF9HWjNqbW5EdusEunk/view))\
    [Bibtex](papers/supercheck21c.bib.html)

29. [Improving Scalability and Reliability of MPI-agnostic Transparent
    Checkpointing for Production Workloads at
    NERSC](https://arxiv.org/abs/2103.08546),\
    Prashant Singh Chouhan, Harsh Khetawat, Neil Resnik, Jain Twinkle,
    Rohan Garg, Gene Cooperman, Rebecca Hartman-Baker, Zhengji Zhao,\
    *First Int. Symp. on Checkpointing for Supercomputing
    (SuperCheck21)*, 4 pages, Feb., 2021, (with [conf.
    program](https://supercheck.lbl.gov/resources),
    [slides](https://drive.google.com/file/d/1SWygVkI5RdfgpBtflheYRJVVzidooevq/view),
    and
    [video](https://drive.google.com/file/d/1POGpC9RQkOwCp1ZAjTGZGlUCTog9ELxU/view))\
    [Bibtex](papers/supercheck21d.bib.html)

30. [So Why Can\'t I Checkpoint That? (keynote
    talk)](https://supercheck.lbl.gov/resources),\
    Gene Cooperman,\
    *First Int. Symp. on Checkpointing for Supercomputing
    (SuperCheck21)*, Feb., 2021, (with [conf.
    program](https://supercheck.lbl.gov/resources),
    [slides](https://drive.google.com/file/d/10c8KWAK0cjROyNZ3OEB2N8CyDu6g_1mg/view),
    and
    [video](https://drive.google.com/file/d/1SHqXJncyHtahr5zu8fmXx53-GawauLXu/view))\
    [Bibtex](papers/supercheck21e.bib.html)

31. [Fault-Tolerant Computing with Heterogeneous Hardening
    Modes](https://library.oapen.org/bitstream/handle/20.500.12657/43279/2021_Book_DependableEmbeddedSystems.pdf?sequence=1#page=170),\
    Florian Kriebel, Faiq Khalid, Bharath Srinivas Prabakaran, Semeen
    Rehman, and Muhammad Shafique,\
    *Dependable Embedded Systems (Embedded Systems series, open
    access)*,\
    eds. Jörg Henkelandand Nikil Dutt, pp. 161\--180, Jan., 2021,
    Springer\
    [Bibtex](papers/dep-emb-sys21.bib.html).

32. [*Direct Heap Snapshotting in the Java HotSpot VM: a
    Prototype*](https://www.diva-portal.org/smash/record.jsf?pid=diva2%3A1508220&dswid=-5259),\
    Ludvig Janiuk,\
    M.S. thesis, KTH Royal Institute of Technology,\
    Dec., 2020,\
    [Bibtex](papers/janiukthesis20.bib).

33. [Soft Errors Detection and Automatic Recovery Based on Replication
    Combined with Different Levels of
    Checkpointing](https://www.sciencedirect.com/science/article/pii/S0167739X19308404),\
    Diego Montezanti, Enzo Rucci, Armando De Giusti, Marcelo Naiouf,
    Dolores Rexachs, and Emilio Luque,\
    *Future Generation Computer Systems* **113**, pp. 240\--254, Dec,
    2020, Elsevier,\
    [Bibtex](papers/future-gen20.bib.html).

34. [*Déploiement Efficace d\'Applications Cloud dans les
    Infrastructures Fog
    Distribuées*](https://tel.archives-ouvertes.fr/tel-02932386/),\
    Arif Ahmed, PhD thesis, U. Rennes 1, Dec., 2020,\
    [Bibtex](papers/ahmedthesis20.bib.html)

35. [Deploying Checkpoint/Restart for Production Workloads at
    NERSC](http://www.ccs.neu.edu/home/gene/papers/sc20-sotp.pdf),\
    Zhengji Zhao, Rebecca Hartman-Baker, Gene Cooperman,\
    *Proc. of the Int. Conf. for High Performance Computing, Networking,
    Storage and Analysis (State of the Practice)* (SC\'20),\
    3 pages, Nov., 2020, IEEE Computer Society,\
    [Bibtex](papers/sc20-sotp.bib)

36. [Containers Runtimes War: A Comparative
    Study](https://link.springer.com/chapter/10.1007/978-3-030-63089-8_9),\
    Ramzi Debab and Walid Khaled Hidouci,\
    *Proc. of Future Technologies Conference (FTC\'10)*, Volume 2,
    pp. 135\--161, Nov., 2020, (*Advances in Intelligent Systems and
    Computing* book series, volume 1289, Springer)\
    [Bibtex](papers/ftc20.bib.html).

37. [*Profiles of Upcoming HPC Applications and Their Impact on
    Reservation
    Strategies*](https://ieeexplore.ieee.org/document/9266751),\
    Ana Gainaru, Brice Goglin, Valentin Honoré, and Guillaume Pallez,\
    *IEEE Trans. on Parallel and Distributed Systems* **32**(5),
    pp. 1178\--1190, Nov, 2020, IEEE Press,\
    [Bibtex](papers/pds20b.bib.html).

38. [Improving Utilization of Heterogeneous
    Clusters](https://link.springer.com/article/10.1007%2Fs11227-020-03175-4),\
    Stafford, Esteban and Bosque, José Luis,\
    *The Journal of Supercomputing* **76**, pp. 8787\--8800, Jan., 2020,
    Springer\
    [Bibtex](papers/jsc20b.bib.html).

39. [Privaros: A Framework for Privacy-Compliant Delivery
    Drones](https://arxiv.org/abs/2002.06512v3),\
    Rakesh Rajan Beck, Abhishek Vijeev, and Vinod Ganapathy,\
    *Proc. of ACM SIGSAC Conference on Computer and Communications
    Security (CCS\'20)*, pp. 181--194 Oct., 2020, ACM Press\
    (and [arXiv preprrint
    arXiv:2002.06512v3](https://arxiv.org/abs/2002.06512))\
    [Bibtex](papers/ccs20.bib).

40. [System-Level vs. Application-Level
    Checkpointing](https://ieeexplore.ieee.org/abstract/document/9229633),\
    Jonas Posner,\
    *Proc. of IEEE Int. Conf. on Cluster Computing (CLUSTER\'20)*,
    pp. 404\--405, Sept., 2020, IEEE Computer Society,\
    [Bibtex](papers/cluster20.bib.html).

41. [*Standard Compliant Snapshotting for SystemC Virtual
    Platforms*](https://publikationsserver.tu-braunschweig.de/servlets/MCRFileNodeServlet/dbbs_derivate_00046888/Diss_Farkas_Bastian.pdf),\
    Bastian Farkas, PhD thesis, Technische Universität Braunschweig,\
    Sept., 2020,\
    [Bibtex](papers/farkasthesis20.bib.html).

42. [Implementation of Resilience as a Service for Parallel
    Computing](https://ieeexplore.ieee.org/abstract/document/9231708),\
    Revina Awalia Putri, Idris Winamo, Wiratmoko Yuwono, and Agus Priyo
    Utomo,\
    *Proc. of International Electronics Symposium (IES\'20)*,
    pp. 626\--630, Sept, 2020,\
    [Bibtex](papers/ies20.bib.html).

43. [Docker Container Deployment in Distributed Infrastructures with
    Checkpoint/Restart
    Fog](https://ieeexplore.ieee.org/document/9126743),\
    Arif Ahmed, Apoorve Mohan, Gene Cooperman, and Guillaume Pierre,\
    *Proc. of 8th IEEE Int. Conf. on Mobile Cloud Computing, Services,
    and Engineering (MobileCloud\'20)*, pp. 55\--62, Aug., 2020, IEEE
    Press\
    (and [HAL Technical Report](https://hal.inria.fr/hal-02473333))\
    [Bibtex](papers/mobilecloud20.bib.html).

44. [Analysis of Checkpoint I/O
    Behavior](https://link.springer.com/chapter/10.1007/978-3-030-50371-0_14),\
    Betzabeth León, Pilar Gomez-Sanchez, Daniel Franco, Dolores Rexachs,
    and Emilio Luque,\
    *International Conference on Computational Science (ICCS\'20)*,
    Lecture Notes in Computer Science **12137**, pp. 191\--205,
    Jun., 2020, Springer\
    (and [ICCS Camera Ready
    Version](https://www.iccs-meeting.org/archive/iccs2020/papers/121370190.pdf))\
    [Bibtex](papers/iccs20.bib.html).

45. [Determinación de la Eficiencia en el Procesamiento sore
    Arquitecturas Multiprocesador y Estrategias de Tolerancia a Fallos
    en HPC](http://sedici.unlp.edu.ar/handle/10915/103560),\
    Jorge Rafael Osio, Diego Miguel Montezanti, Marcelo Angel
    Cappelletti, Eduardo Kunysz, and Martín Morales,\
    *XXII Workshop de Investigadores en Ciencias de la Computación
    (WICC\'20)*, El Calafate, Santa Cruz (Argentina), May, 2020,\
    [Bibtex](papers/wicc20b.bib.html).

46. [Resumen de Tesis: SEDAR: Detecciónn y Recuperación Automática de
    Fallos Transitorios en Sistemas de Cómputo de Altas
    Prestaciones](http://sedici.unlp.edu.ar/handle/10915/76955),\
    (Thesis summary: SEDAR: Detection and Automatic Recovery from
    Transient Faults in High Performance Computing Systems)\
    Diego Montezanti,\
    *XXII Workshop de Investigadores en Ciencias de la Computación
    (WICC\'20)*, El Calafate, Santa Cruz (Argentina), May, 2020\
    [Bibtex](papers/wicc20a.bib.html)

47. [Middleware to Manage Fault Tolerance Using Semi-Coordinated
    Checkpoints](https://ieeexplore.ieee.org/abstract/document/9165191),\
    Alvaro Wong, Elisa Heymann, Dolores Rexachs and Emilio Luque,\
    *IEEE Trans. on Parallel and Distributed Systems* **32**(2),
    pp. 254\--268, May, 2020, IEEE Press,\
    [Bibtex](papers/pds20a.bib.html).

48. [Elastic Execution of Checkpointed MPI
    Applications](https://arxiv.org/abs/2005.07543),\
    Sumeet Gajjar and Saurabh Vaidya,\
    6 pages, May, 2020, arXiv preprint arXiv:2005.07543,\
    [Bibtex](papers/arxiv20a.bib.html).

49. [Systèmes Résilients pour l\'Automobile : d\'une Approche à
    Composants à une Approche à Objets de la Tolérance aux Fautes
    Adaptative sur ROS](https://oatao.univ-toulouse.fr/26007/),\
    Matthieu Amy, PhD thesis,\
    Institut National Polytechnique de Toulouse, May, 2020\
    [Bibtex](papers/amythesis20.bib.html)

50. [SEDAR: Detecciónn y Recuperación Automática de Fallos Transitorios
    en Sistemas de Cómputo de Altas
    Prestaciones](http://sedici.unlp.edu.ar/handle/10915/98816),\
    (SEDAR: Detection and Automatic Recovery from Transient Faults in
    High Performance Computing Systems),\
    Diego Miguel Montezanti, PhD thesis,\
    Universidad Nacional de la Plata, Mar., 2020\
    [Bibtex](papers/montezantithesis20.bib.html)

51. [*GIFT: A Coupon Based Throttle-and-Reward Mechanism for Fair and
    Efficient I/O Bandwidth Management on Parallel Storage
    Systems*](https://www.usenix.org/conference/fast20/presentation/patel-gift),\
    Tirthak Patel, Rohan Garg, and Devesh Tiwari, *18th USENIX Conf. on
    File and Storage Technologies (FAST\'20)*, Feb., 2020,\
    [Bibtex](papers/fast20.bib.html).

52. [IaaS Cloud as a Virtual Environment for Experimentation in
    Checkpoint
    Analysis](http://journal.info.unlp.edu.ar/JCST/article/view/1267),\
    Betzabeth Leén, Pilar Gomez-Sanchez, Daniel Franco, Dolores Rexachs,
    and Emilio Luque,\
    *Journal of Computer Science and Technology (JCS&T) **19**(2)*,
    pp. 110\--122, Oct., 2019,\
    [Bibtex](papers/jcst19.bib.html).

53. [SEDAR: Detectando y Recuperando Fallos Transitorios en Aplicaciones
    de HPC](http://sedici.unlp.edu.ar/handle/10915/90527),\
    Diego Miguel Montezanti, Enzo Rucci, Dolores Rexachs del Rosario,
    Emilio Luque Fadón, Marcelo Naiouf, and Armando Eduardo De Giusti,\
    *XXV Congreso Argentino de Ciencias de la Computación (CACIC\'19)*,\
    (Universidad Nacional de Río Cuarto Córdoba, Oct., 2019)\
    [Bibtex](papers/cacic19.bib.html)

54. [Process Migration-based Computational Offloading Framework for
    IoT-supported Mobile Edge/Cloud
    Computing](https://arxiv.org/pdf/1909.11058.pdf),\
    Abdullah Yousafzai, Ibrar Yaqoob, Muhammad Imran, Abdullah Gani, and
    Rafidah Md Noor,\
    *Internet of Things Journal* **7**(5),\
    pp. 4171\--4182, Sept., 2019, IEEE Press,
    [Bibtex](papers/iotj19.bib.html)

55. [Checkpointing the Un-checkpointable: MANA and the Split-Process
    Approach](http://mug.mvapich.cse.ohio-state.edu/static/media/mug/presentations/19/cooperman-mug-19.pdf),\
    Gene Cooperman,\
    *MVAPICH User Group (MUG\'19)*,\
    Columbus, Ohio, Aug. 20, 2019; [MUG\'19
    program](http://mug.mvapich.cse.ohio-state.edu/program/),
    [slides](http://mug.mvapich.cse.ohio-state.edu/static/media/mug/presentations/19/cooperman-mug-19.pdf);\
    [video](https://www.youtube.com/watch?v=hO9G8W_gmEc) (from
    <https://insidehpc.com/2019/09/checkpointing-the-un-checkpointable-mana-and-the-split-process-approach/>);\
    [Bibtex](papers/mug19.bib).

56. [Architectural-Space Exploration of Heterogeneous Reliability and
    Checkpointing Modes for Out-of-Order Superscalar
    Processors](https://ieeexplore.ieee.org/document/8622785),\
    Bharath Srinivas Prabakaran, Mihika Dave, Florian Kriebel, Semeen
    Rehman, and Muhammad Shafique,\
    *IEEE Access **7***,\
    pp. 145324\--145339, Jul.. 2019, IEEE Press,\
    (Also as [arXiv tech. report](https://arxiv.org/abs/1811.07612v3))\
    [Bibtex](papers/ieee-access19b.bib.html).

57. [Checkpoint/Restart Approaches for a Thread-based MPI
    Runtime](https://arxiv.org/pdf/1906.05020.pdf),\
    Julien Adam, Maxime Kermarquer, Jean-Baptiste Besnard, Leonardo
    Bautista-Gomez, Marc Pérache, Patrick Carribault, Julien Jaeger,
    Allen D Malony, and Sameer Shende,\
    *Parallel Comkputing **85***, pp. 204\--219, Jul., 2019, Elsevier
    [Bibtex](papers/par-comp19.bib.html).

58. [*Resilience in high-level parallel programming
    languages*](https://openresearch-repository.anu.edu.au/handle/1885/164137),\
    Sara S. Hamouda, PhD thesis, The Australian National University,
    Jun., 2019,\
    [Bibtex](papers/hamoudathesis19.bib.html)

59. [*Extending the Domain of Transparent Checkpoint-Restart for
    Large-scale HPC*](http://hdl.handle.net/2047/D20316244),\
    Rohan Garg, PhD thesis, Northeastern U., May, 2019,\
    [Bibtex](papers/gargthesis19.bib)

60. [Exploring Semantic Reverse Engineering for Software Binary
    Protection](https://rucore.libraries.rutgers.edu/rutgers-lib/61117/),\
    Pengfei Sun, PhD thesis,\
    Ruthers,The State University of New Jersey, May, 2019\
    [Bibtex](papers/sunthesis19.bib.html)

61. [Active Replication for Centrally Coordinated Teams of Autonomous
    Vehicles](http://www.pvautoscout.com/wp-content/uploads/2019/05/dcoss19-paper12.pdf),\
    Nasos Grigoropoulos, and Manos Koutsoubelias, and Spyros Lalis,\
    *15th Int. Conf. on Distributed Computing in Sensor Systems
    (DCOSS\'19)*,\
    pp. 114\--122, May, 2019, IEEE Press,
    [Bibtex](papers/dcoss19.bib.html)

62. [Prediction of Energy Consumption by Checkpoint/Restart in
    HPC](https://ieeexplore.ieee.org/document/8727526),\
    Marina Morán, Javier Balladini, Dolores Rexachs, and Emilio Luque,\
    *IEEE Access **7***,\
    pp. 71791\--71803, May, 2019, IEEE Press,\
    [Bibtex](papers/ieee-access19a.bib.html).

63. [Determinación de la eficiencia y estrategias de tolerancia a fallos
    en arquitecturas multiprocesador para aplicaciones de procesamiento
    de datos](http://sedici.unlp.edu.ar/handle/10915/76955),\
    Jorge Rafael Osio, Diego Miguel Montezanti, Eduardo Kunysz, and
    Daniel Martin Morales,\
    *XXI Workshop de Investigadores en Ciencias de la Computación
    (WICC\'19)*, Apr., 2019, Universidad Nacional de San Juan
    (Argentina), [Bibtex](papers/wicc19.bib.html)

64. [Job Migration in HPC Clusters by Means of
    Checkpoint/Restart](https://link.springer.com/article/10.1007/s11227-019-02857-y),\
    Manuel Rodríguez-Pascual, Jiajun Cao, José A. Moríñigo, Gene
    Cooperman, Rafael Mayo-García,\
    *The Journal of Supercomputing* **75**(10), pp. 6517\--6541, online
    Apr., 2019, Springer, [Bibtex](papers/jsc19.bib.html)

65. [Resource Manager for Scalable Performance in ROS Distributed
    Environments](https://ieeexplore.ieee.org/abstract/document/8715030/),\
    Daisuke Fukutomi, Takuya Azumi, Shinpei Kato, and Nobuhiko Nishio,\
    *Design, Automation \\& Test in Europe Conference \\& Exhibition
    (DATE\'19)*,\
    pp. 1088\--1093, Mar., 2019, IEEE Press,
    [Bibtex](papers/date19.bib.html)

66. [Checkpointing and Migration of IoT Edge
    Functions](https://dl.acm.org/citation.cfm?id=3313947),\
    Pekka Karhula, and Jan Janak, and Henning Schulzrinne,\
    *Proc. of 2nd Int. Workshop on Edge Systems, Analytics and
    Networking (EdgeSys\'19; co-located with EuroSys\'19)*, pp. 60-65,
    Mar., 2019, ACM Press, [Bibtex](papers/edgesys19.bib.html)

67. [Uma Taxonomia de Sistemas de Tolerância a Falhas em Ambientes de
    Computação em Nuvem Open
    Source](https://repositorio.unesp.br/handle/11449/182088),\
    Vinicius Santos Andrade, M.S. thesis, Universidade Estadual Paulista
    \"Jûlio de Mesquita Filho\", Jan., 2019\
    [Bibtex](https://dmtcp.sourceforge.io/papers/andrade19.bib)

68. [*Elastic Scheduling in HPC Resource Management
    Systems*](https://conservancy.umn.edu/handle/11299/202169),\
    Feng Liu, PhD thesis, University of Minnesota, Dec., 2018,\
    [Bibtex](papers/liu18.bib.html)

69. [H-RADIC: A Fault Tolerance Framework for Virtual Clusters on
    Multi-Cloud
    Environments](http://journal.info.unlp.edu.ar/JCST/article/view/1150),\
    Ambrosio Royo, Jorge Villamayor, Marcela Castro-León, Dolores
    Rexachs, and Emilio Luque,\
    *Journal of Computer Science and Technology (JCS&T) **18**(3)*,
    pp. e24\--e24, Dec., 2018, Springer,
    [Bibtex](papers/jcst18.bib.html).

70. [*Autonomic Approach based on Semantics and Checkpointing for IoT
    System Management*](https://hal.laas.fr/tel-02007331/document),\
    François Aïssaoui, PhD thesis, Toulouse 1, Nov., 2018,\
    [Bibtex](papers/aissaouithesis18.bib.html)

71. [Checkpoint and Restart: An Energy Consumption
    Characterization](https://link.springer.com/chapter/10.1007/978-3-030-20787-8_2),\
    Marina Morán, Javier Balladini, Dolores Rexachs, and Emilio Luque,\
    *Argentine Congress of Computer Science (CACIC\'18)*,\
    pp. 19\--33, Oct., 2018, Springer,\
    (Also appearing in Spanish as: [Factores que afectan el consumo
    energético de operaciones de checkpoint y restart en clusters (XIX
    Workshop Prcoesamiento Distribuido y Paralelo (WPDP) of
    CACIC\'18)](http://sedici.unlp.edu.ar/handle/10915/73036), with
    [pdf](http://sedici.unlp.edu.ar/bitstream/handle/10915/73036/Documento_completo.pdf-PDFA.pdf?sequence=1)),
    [Bibtex](papers/cacic18.bib.html)

72. [*Programming and Testing Support for Drone Based
    Applications*](https://core.ac.uk/download/pdf/161850147.pdf),\
    Manos Koutsoubelias, PhD thesis, University of Thessaly (Greece),
    Sept., 2018,\
    [Bibtex](papers/koustsoubeliathesis18.bib.html).

73. [*Resource Management for Extreme Scale High Performance Computing
    Systems in the Presence of
    Failures*](https://mountainscholar.org/handle/10217/191485),\
    Daniel Dauwe, PhD thesis, Colorado State University, Sept., 2018,\
    [Bibtex](https://dmtcp.sourceforge.io/papers/dauwe18.bib)

74. [Transparent High-Speed Network Checkpoint/Restart in
    MPI](https://dl.acm.org/citation.cfm?id=3236383),\
    Julien Adam, Jean-Baptiste Besnard, Allen D Malony, Sameer Shende,
    PéMarc rache, Patrick Carribault, Julien Jaeger,\
    *Proc. of 25th European MPI User Group Meeting*,\
    ACM, 12 pages, Sept., 2018, [Bibtex](papers/eurompi18.bib.html).

75. [Fault Tolerance in Cloud Computing Environment: A Systematic
    Survey](https://www.sciencedirect.com/science/article/abs/pii/S0166361517304438),\
    Moin Hasan, and Major Singh Goraya,\
    *Computers in Industry* **99**, pp. 156\--172, Aug., 2018, Elsevier,
    [Bibtex](papers/comp-ind18.bib.html)

76. [Characterization of I/O Patterns generated by Fault Tolerance in
    HPC
    environments](https://csce.ucmss.com/cr/books/2018/LFS/CSREA2018/PDP3611.pdf),\
    Betzabeth Lén, Daniel Franco, Dolores Rexachs, and Emilio Luque,\
    *Proc. of Int. Conf. on Parallel and Distributed Processing
    Techniques and Applications (PDPTA\'18)*, pp. 28\--34, Jul.. 2018\
    [Bibtex](papers/pdpta18.bib).

77. [Leveraging the Checkpoint-Restart Technique for Optimizing CPU
    Efficiency of ATLAS Production Applications on Opportunistic
    Platforms](https://dmtcp.sourceforge.io/%5Dhttps://iopscience.iop.org/article/10.1088/1742-6596/1085/3/032028/pdf),\
    D. Cameron, J. Elmsheuser, L. Heinrich, W. Lavrijsen, P. Nilsson,
    V. Tsulaia, M. Vogel on behalf of the ATLAS Collaboration,\
    5 pages, 2018, IOPScience **1085** (2018)032028,\
    [Bibtex](https://dmtcp.sourceforge.io/papers/acat2017). *(See
    preprint version, below, also by Cameron et al.)*

78. [Checkpointing a Subsystem
    Remotely](http://mug.mvapich.cse.ohio-state.edu/static/media/mug/presentations/18/cooperman-mug-18.pdf),\
    Gene Cooperman,\
    *MVAPICH User Group (MUG\'18)*,\
    Columbus, Ohio, Aug. 7, 2018; [MUG\'18
    program](http://mug.mvapich.cse.ohio-state.edu/mug/18/),
    [slides](http://mug.mvapich.cse.ohio-state.edu/static/media/mug/presentations/18/cooperman-mug-18.pdf);\
    [Bibtex](papers/mug18.bib.html).

79. [Automatic Characterization of HPC Job Parallel Filesystem I/O
    Patterns](https://dl.acm.org/doi/abs/10.1145/3219104.3219121),\
    Joseph P White, Alexander D Kofke, Robert L DeLeon, Martins Innus,
    Matthew D Jones, and Thomas R Furlani,\
    *Proc. of the Practice and Experience on Advanced Research Computing
    (PEARC\'18)*,\
    pp. 1\--8, July, 2018, [Bibtex](papers/pearc18.bib).

80. [Shiraz: Exploiting System Reliability and Application Resilience
    Characteristics to Improve Large Scale System
    Throughput](http://www.ccs.neu.edu/home/gene/papers/dsn18.pdf),\
    Rohan Garg, Tirthak Patel, Gene Cooperman, and Devesh Tiwari,\
    *48th Annual IEEE/IFIP Int. Conf. on Dependable Systems and Networks
    (DSN\'18)*,\
    IEEE, pp. 83\--94, July, 2018, [Bibtex](papers/dsn18.bib.html).

81. [Fault-Tolerance Support for Mobile Robotic
    Applications](https://ieeexplore.ieee.org/abstract/document/8442098),\
    Manos Koutsoubelias and Spyros Lalis,\
    *13th Int. Symp. on Industrial Embedded Systems (SIES\'18)*,\
    IEEE, pp. 1\--10, June, 2018, [Bibtex](papers/sies18.bib.html).

82. [RaaS: Resilience as a
    Service](https://ieeexplore.ieee.org/abstract/document/8411044/references#references),\
    Jorge Villamayor, Dolores Rexachs, Emilio Luque, Diego Lugones,\
    *Proc. 18th IEEE/ACM Int. Symp. on Cluster, Cloud and Grid Computing
    (CCGRID\'18)*,\
    IEEE, pp. 356\--359, May, 2018, [Bibtex](papers/ccgrid18.bib.html).

83. [CDBB: an NVRAM-based Burst Buffer Coordination System for Parallel
    File Systems](https://dl.acm.org/citation.cfm?id=3213070),\
    Ziqi Fan, Fenggang Wu, Jim Diehl, David HC Du, and Doug Voigt,\
    *Proc. of the High Performance Computing Symposium (HPC\'18)*,\
    pp. 1:1\--1:12, Apr., 2018, ACM Press,\
    Society for Computer Simulation International,
    [Bibtex](papers/hpc18.bib.html).

84. [Transparently Checkpointing Software Test Benches to Improve
    Productivity of SoC Verification in an Emulation
    Environment](https://dvcon-proceedings.org/document/transparently-checkpointing-software-test-benches-to-improve-productivity-of-soc-verification-in-an-emulation-environment/),\
    Ankit Garg, Suresh Krishnamurthy, Gene Cooperman, Rohan Garg, and
    Jeff Evans,\
    *2018 Design and Verification Conference and Exhibition (DVCON-US
    2018)*,\
    San Jose, CA, Feb. 27, 2018; [DVCON-US
    2018](https://dvcon-proceedings.org/choose-your-location/united-states/),\
    [slides](https://dvcon-proceedings.org/document/transparently-checkpointing-software-test-benches-to-improve-productivity-of-soc-verification-in-an-emulation-environment-presentation/),
    [Bibtex](papers/dvcon-us18.bib.html).\
    *(IMPORTANT: Browser must allow popups, to view paper at DVCon
    site.)*

85. [*Transparent checkpointing over RDMA-based
    networks*](http://hdl.handle.net/2047/D20290419),\
    Jiajun Cao, PhD thesis, Northeastern U., Dec., 2017,\
    [Bibtex](papers/caothesis17.bib.html)

86. [ITALC: Interactive Tool for Application-Level
    Checkpointing](https://dl.acm.org/citation.cfm?id=3152558),\
    Ritu Arora and Trung Nguyen Ba,\
    *Proc. of Fourth International Workshop on HPC User Support Tools
    (HUST\'17)*,\
    Nov., 2017;
    ([slides](https://hust17.github.io/2017_presentations/ITALC.pdf)),
    [Bibtex](papers/hust17.bib).

87. [E-HPC: a Library for Elastic Resource Management in HPC
    Environments\>](https://dl.acm.org/citation.cfm?id=3150996),\
    William Fox, Devarshi Ghoshal, Abel Souza, Gonzalo P Rodrigo, and
    LavanyaRamakrishnan,\
    *Proc. of the 12th Workshop on Workflows in Support of Large-Scale
    Science*,\
    Nov., 2017; [Bibtex](papers/works17.bib).

88. [Constructing the Formal Grammar of System
    Calls](https://dl.acm.org/citation.cfm?id=3166106),\
    Nikolay Efanovand and Pavel Emelyanov,\
    *Proc. 13th Central & Eastern European Software Engineering
    Conference in Russia*,\
    Oct., 2017; [Bibtex](papers/eesec17.bib).

89. [Selective Checkpointing for Minimizing Recovery Energy and Efforts
    of Smartphone
    Apps](https://ieeexplore.ieee.org/abstract/document/8323571),\
    Li Li, Yunhao Bai, Xiaorui Wang, Mai Zheng, and Feng Qin,\
    *Eighth Int. Green and Sustainable Computing Conference
    (IGSC\'17)*,\
    IEEE, pp. 1\--8, Oct., 2017; [Bibtex](papers/igsc17.bib.html).

90. [Leveraging the Checkpoint-restart Technique for Optimizing CPU
    Efficiency of ATLAS Production Applications on Opportunistic
    Platforms](https://cds.cern.ch/record/2286989/files/ATL-SOFT-PROC-2017-054.pdf),\
    D. Cameron, J. Elmsheuser, L. Heinrich, W. Lavrijsen, P. Nilsson,
    V. Tsulaia, M. Vogel on behalf of the ATLAS Collaboration,\
    *ATL-SOFT-PROC-2017-064*,\
    Oct., 2017; [Bibtex](papers/atl17.bib).

91. [When you have a hammer, everything is a nail: Checkpoint/Restart in
    Slurm](https://slurm.schedmd.com/slurm_ug_agenda.html),\
    Manuel Rodríguez-Pascual, Jose Antonio Moríñigo, and Rafael
    Mayo-García,\
    *Slurm User Group Meeting --- 2017*,\
    Berkeley, CA, Sept. 26, 2017; [Slurm User Group
    Agenda](https://slurm.schedmd.com/slurm_ug_agenda.html) (accessed
    Oct., 2017);\
    [Bibtex](papers/slurm17.bib.html).

92. [DMTCP: Fixing the Single Point of Failure of the ROS
    Master](https://roscon.ros.org/2017/),\
    Gene Cooperman and Twinkle Jain,\
    *ROSCon 2017*,\
    Vancouver, Canada, Sept. 21, 2017; [ROSCon\'17
    program](https://roscon.ros.org/2017/),
    [slides](https://roscon.ros.org/2017/presentations/ROSCon%202017%20DMTCP.pdf);\
    [video](https://vimeo.com/236166291);\
    [Bibtex](papers/roscon17.bib).

93. [Expedite any Simulation with DMTCP and Save Decades of
    Computation](https://dvcon-proceedings.org/document/expedite-any-simulation-with-dmtcp-and-save-decades-of-computation-presentation/),\
    Balaji R (presenting), Sathish Kumar Sugumara, Gene Cooperman, Rohan
    Garg, and Jiajun Cao,\
    *2017 Design and Verification Conference and Exhibition (DVCON-India
    2017)*,\
    Bengalauru, India, Sept. 15, 2017; [DVCON-India
    2017](https://dvcon-india.org/),\
    [Bibtex](papers/dvcon-india17.bib.html).\

94. [Intelligent Checkpointing Strategies for IoT System
    Management](https://hal.laas.fr/hal-01807513/document),\
    Aïssaoui, François and Cooperman, Gene and Monteil, Thierry and
    Tazi, Saïd,\
    *Future Internet of Things and Cloud (FiCloud\'17)*,\
    IEEE, pp. 305\--312, Aug., 2017;
    [Bibtex](papers/ficloud17.bib.html).

95. [Extending DMTCP Checkpointing for a Hybrid Software
    World](http://mug.mvapich.cse.ohio-state.edu/static/media/mug/presentations/17/cooperman-mug-17.pdf),\
    Gene Cooperman,\
    *MVAPICH User Group (MUG\'17)*,\
    Columbus, Ohio, Aug. 16, 2017; [MUG\'17
    program](http://mug.mvapich.cse.ohio-state.edu/mug/17/),
    [slides](http://mug.mvapich.cse.ohio-state.edu/static/media/mug/presentations/17/cooperman-mug-17.pdf);\
    [video](https://www.youtube.com/watch?v=5omfeh15Fq4);\
    [Bibtex](papers/mug17.bib.html).

96. [A Methodology for Soft Errors Detection and Automatic
    Recovery](https://www.computer.org/csdl/proceedings/hpcs/2017/3250/00/08035110.pdf),\
    Jorge Villamayor, Dolores Rexachs, Emilio Luque, Diego
    Montezanti, A. De Giusti, and M. Naiouf,\
    *Int. Conf. on High Performance Computing & Simulation*,\
    July, 2017; [Bibtex](papers/hpcs17c.bib.html).

97. [When is the Right Time to Start the Fault Tolerance
    Protection?](https://www.computer.org/csdl/proceedings/hpcs/2017/3250/00/08035109.pdf),\
    Jorge Villamayor, Dolores Rexachs, and Emilio Luque,\
    *Int. Conf. on High Performance Computing & Simulation*,\
    July, 2017; [Bibtex](papers/hpcs17b.bib).

98. [A Fault Tolerance Manager with Distributed Coordinated Checkpoints
    for Automatic
    Recovery](https://www.computer.org/csdl/proceedings/hpcs/2017/3250/00/08035112.pdf),\
    Jorge Villamayor, Dolores Rexachs, and Emilio Luque,\
    *Int. Conf. on High Performance Computing & Simulation (HPCS-17)*,\
    July, 2017; [Bibtex](papers/hpcs17a.bib.html).

99. [Performance of Android Cluster System Allowing Dynamic Node
    Reconfiguration](https://link.springer.com/article/10.1007/s11277-017-3978-9),\
    Yuki Sawada, Yusuke Arai, Kanemitsu Ootsu, Takashi Yokota, and
    Takesh Ohkawa,\
    *?Wireless Personal Communications*, **93**(4), pp. 1067\--1087,
    April, 2017, Springer,\
    [Bibtex](papers/wireless-comm17.bib.html)

100. [Transition Watchpoints: Teaching Old Debuggers New
     Tricks](https://arxiv.org/pdf/1703.10864.pdf),\
     Kapil Arya, Tyler Denniston, Ariel Rabkin, and Gene Cooperman,\
     *[The Art, Science, and Engineering of
     Programming](http://programming-journal.org/2017/1/16/)***1**(2),\
     28 pages, Apr., 2017; [Bibtex](papers/prog17.bib.html).

101. [Fault Tolerance and Message Passing Interface
     Programs](https://web.a.ebscohost.com/abstract?jrnl=09765697&AN=122961204&h=HuFZHC8oEkZ8vYlLsqJ39pvVXNUQvgwz%2fls4El7DZxFP6oReUJoxhIi21Tc86e6xWS4l%2faOriy6Dq9Rik013TA%3d%3d&crl=c&crlhashurl=login.aspx%3fdirect%3dtrue%26profile%3dehost%26scope%3dsite%26authtype%3dcrawler%26jrnl%3d09765697%26AN%3d122961204),\
     Mohammad Miyan,\
     *Int. J. of Advanced Research in Computer Science*,\
     pp. 128\--135, Mar/Apr, 2017; [Bibtex](papers/arcs17.bib.html).

102. [A Reflexive Tactic for Polynomial Positivity using Numerical
     Solvers and Floating-point
     Computations](https://hal.archives-ouvertes.fr/hal-01510979/document),\
     Érik Martin-Dorel and Pierre Roux,\
     ACM SIGPLAN Conference on Certified Programs and Proofs (CPP 2017),
     pp. 90\--99, Jan., 2017, ACM,\
     [Bibtex](papers/cpp17.bib.html)

103. [DMTCP: Deadline-aware Multipath
     TCP](http://ieeexplore.ieee.org/document/7962737/),\
     Huang, Chengyuan, Zhang, Jiao, Huang, Tao and Liu, Yunjie,\
     *Proc. of Communications Workshops* (2017 IEEE Int. Conf. on ICC),
     pp. 681\--686, May, 2017, IEEE,\
     [Bibtex](papers/icc-comm17.bib.html)

104. [A Performance and Energy Comparison of Fault Tolerance Techniques
     for Exascale Computing
     Systems](http://www.engr.colostate.edu/~hj/conferences/366.pdf),\
     D. Dauwe, S. Pasricha, A. A. Maciejewski, and H. J. Siegel,\
     *IEEE Int. Conf. on Computer and Information Technology
     (CIT\'16)*,\
     pp. 436\--443, Dec., 2016, IEEE,\
     [Bibtex](papers/cit16.bib.html)

105. [Trace-free Memory Data Structure Forensics via Past Inference and
     Future Speculations](http://dl.acm.org/citation.cfm?id=2991118),\
     Penfei Sun, Rui Han, Mingbo Zhang and Saman Zonouz,\
     *Proc. of 32nd Annual Conf. on Computer Security Applications*,
     pp. 570\--582, Dec., 2016, ACM,\
     [Bibtex](papers/csa16.bib)

106. [Smart Scene Management for IoT-based Constrained Devices using
     Checkpointing](http://www.ccs.neu.edu/home/gene/papers/nca16b.pdf),\
     François Aïssaoui, Gene Cooperman, Thierry Monteil, and Saïd Tazi,\
     *15th IEEE Int. Symp. on Network Computing and Applications
     (NCA\'16)*,\
     Cambridge, MA, USA, Oct. 31 - Nov. 2, 2016, pp. 170\--174, IEEE
     Press, Nov., 2016,\
     [Bibtex](papers/nca16.bib.html)

107. [Adaptive Fault Tolerance on ROS: A Component-Based
     Approach](https://roscon.ros.org/2016/presentations/ROSCon2016_Adaptive_Fault_Tolerance.pdf),\
     Jean-Charles Fabre, Michaël Lauer, Matthieu Amy,\
     *[ROSCon 2016](https://roscon.ros.org/2016/)*,
     [slides](https://roscon.ros.org/2016/presentations/ROSCon2016_Adaptive_Fault_Tolerance.pdf)
     and [video](https://vimeo.com/187699448) only, Oct., 2016,\
     [Bibtex](papers/roscon16.bib.html)

108. [Applying Future Exascale HPC Methodologies in the Energy
     Sector](https://upcommons.upc.edu/bitstream/handle/2117/90905/Applying%20future%20Exascale%20HPC%20methodologies%20in%20the%20energy%20sector.pdf),\
     José J Camata, José M Cela, Danilo Costa, Alvaro LGA Coutinho,
     Daniel Fernández-Galisteo, Carmen Jiménez, Vadim Kourdioumov, Marta
     Mattoso, Rafael Mayo-García, Thomas Miras, and J.A. Moríñigo,\
     *[Proc. of Russian Supercomputing
     Days 2016](http://RussianSCDays.org)*, p. 9\--19, Sept., 2016,
     [UPCommons](https://upcommons.upc.edu/handle/2117/90905),\
     [Bibtex](papers/russianscdays16.bib)

109. [Deduplication Potential of HPC Applications\'
     Checkpoints](http://ieeexplore.ieee.org/document/7776537/){<=""},\
     Jürgen Kaiser, Ramy Gad, Tim Süß, Federico Padua, Lars Nagel and
     André Brinkmann,\
     *Proc. of IEEE Int. Conf. on Cluster Computing (Cluster\'16)*,\
     pp. 413\--422, Taipei, Taiwan, IEEE Press, Sept., 2016,\
     [Bibtex](papers/cluster16b.bib.html)

110. [Enhancing Energy Production with Exascale HPC
     Methods](https://link.springer.com/chapter/10.1007/978-3-319-57972-6_17)
     *(and [prior technical
     report](https://upcommons.upc.edu/bitstream/handle/2117/100183/Enhancing%20Energy%20Production%20with%20Exascale%20HPC.pdf))*,\
     Rafael Mayo-García, José J. Camata, José M.Cela, Danilo Costa,
     Alvaro LGA Coutinho, Daniel Fernández-Galiste, Carmen Jiménez,
     Vadim Kourdioumov, Marta Mattoso, Thomas Miras, José A. Moríñigo,
     Jorge Navarro; Philippe O. A. Navaux, Daniel de Oliveira, Manuel
     Rodríguez-Pascual, Vítor Silva, Renan Souza, and Patrick
     Valduriez,\
     *Latin American High Performance Computing Conference* (CARLA\'16),
     pp. 233\--246, Aug., 2016, Springer (Communications in Computer and
     Information Science book series, CCIS, vol. 697),\
     [Bibtex](papers/carla16.bib.html)

111. [Scalable System-level Transparent Checkpointing for
     OpenSHMEM](http://www.ccs.neu.edu/home/gene/papers/openshmem16.pdf),\
     Rohan Garg, Jérôme Vienne and Gene Cooperman,\
     *OpenSHMEM and Related Technologies. Enhancing OpenSHMEM for Hybrid
     Environments \-\-- Third Workshop,\
     OpenSHMEM 2016, Baltimore, MD, USA, Aug. 2\--4, 2016, Revised
     Selected Papers (OpenSHMEM\'16)*,\
     pp. 52\--65, Lecture Notes in Computer Science, Volume 10007,
     Springer-Verlag, Aug., 2016,\
     [Bibtex](papers/openshmem16.bib.html)

112. [Extended Batch Sessions and Three-Phase Debugging: Using DMTCP to
     Enhance the Batch
     Environment](http://www.ccs.neu.edu/home/gene/papers/xsede16.pdf),\
     Rohan Garg, Jiajun Cao, Kapil Arya, Gene Cooperman and Jérôme
     Vienne,\
     *Proc. of the (XSEDE16) Conference on Diversity, Big Data, and
     Science at Scale*,\
     pp. 42:1\--42:8, ACM Press, July, 2016, ([and
     slides](https://www.xsede.org/documents/10157/1125659/XSEDE_ECSS_2016.pdf)),\
     [Bibtex](papers/xsede16.bib).

113. *Computational Studies of De Novo Motif Discovery in Aptamer
     Selections*,\
     Kevin R. Shieh, PhD thesis, Yeshiva University, 2016,\
     [Bibtex](https://dmtcp.sourceforge.io/shiehthesis16.bib)

114. [A Checkpointing Methodology for Android
     Smartphone](https://etd.ohiolink.edu/!etd.send_file?accession=osu1461171667),\
     Yunhao Bai, M.S. thesis, The Ohio State University, 2016,\
     [Bibtex](papers/baithesis16.bib.html)

115. [Checkpointing with DMTCP and MVAPICH2 for
     Supercomputing](http://mug.mvapich.cse.ohio-state.edu/static/media/mug/presentations/2016/Kapil_Arya_MUG16.pdf),\
     Kapil Arya,\
     *MVAPICH User Group (MUG\'16)*,\
     Columbus, Ohio, Aug. 17, 2016; [MUG\'16
     program](http://mug.mvapich.cse.ohio-state.edu/mug/16/),
     [slides](http://mug.mvapich.cse.ohio-state.edu/static/media/mug/presentations/2016/Kapil_Arya_MUG16.pdf);\
     [Bibtex](papers/mug16.bib.html).

116. [Simulation Infrastructure for the Study of
     Performance/QOS/Energy](https://core.ac.uk/download/pdf/159408051.pdf),\
     Georgios Ioannis Kopanas,\
     *Diploma Thesis*, U. of Thessaly\
     Feb., 2016, [Bibtex](papers/diploma16.bib).

117. [An Affinity-structure Database of Helix-turn-helix: DNA Complexes
     with a Universal Coordinate
     System](https://bmcbioinformatics.biomedcentral.com/articles/10.1186/s12859-015-0819-2),\
     Mohammed and AlQuraishi, Shengdong Tang and Xide Xia,\
     *BMC Bioinformatics* **16**:390, 19 pages, 2015, BioMed Central,\
     [Bibtex](papers/bmc15.bib.html).

118. [HOL (y) Hammer: Online ATP Service for HOL
     Light](http://link.springer.com/article/10.1007/s11786-014-0182-0),\
     Cezary Kaliszyk and Josef Urban,\
     *Mathematics in Computer Science* **9**(1), pp. 5\--22, 2015,
     Springer,\
     (first published online on Jun 28, 2014)\
     [Bibtex](papers/mcs15.bib.html).

119. [Parallel Application Signature for Performance Analysis and
     Prediction](http://ieeexplore.ieee.org/xpls/abs_all.jsp?arnumber=6827943)
     (or
     [alt](http://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=6827943)),\
     Alvaro Wong, Dolores Rexachs, Emilio Luque,\
     *IEEE Trans. on Parallel and Distributed Systems* **26**(7),
     pp. 2009\--2019, 2015, IEEE Press,\
     [Bibtex](papers/pds15.bib.html).

120. [Elastic Job Bundling: An Adaptive Resource Request Strategy for
     Large-scale Parallel
     Applications](http://dl.acm.org/citation.cfm?id=2807610) (or
     [alt](https://www.cs.umn.edu/sites/cs.umn.edu/files/tech_reports/15-006.pdf)),\
     Feng Liu and Jon B. Weissman,\
     *Proc. of the Int. Conf. for High Performance Computing,
     Networking, Storage and Analysis (SC\'15)*, 12 pages, Nov., 2015,
     ACM,\
     [Bibtex](papers/sc15.bib).

121. [Performance Improvement in Automata Learning: Speeding up LearnLib
     using Parallelization and
     Checkpointing](http://www.ru.nl/publish/pages/769526/z_masterthesismhenrix_marco_henrix.pdf),\
     Marco Henrix,\
     M.S. thesis, Radboud University Nijmegen, Netherlands, Aug., 2015,\
     [Bibtex](papers/henrixthesis15.bib.html).

122. [An Android Cluster System Capable of Dynamic Node
     Reconfiguration](http://ieeexplore.ieee.org/xpl/login.jsp?tp=&arnumber=7182632),\
     Yuki Sawada, Yusuke Arai, Kanemitsu Ootsu, Takashi Yokota and
     Takeshi Ohkawa,\
     *Proc. of 2015 Seventh Int. Conf. on Ubiquitous and Future Networks
     (ICUFN)*, pp. 689\--694, IEEE Press, July, 2015,\
     [Bibtex](papers/icufn15.bib.html).

123. [Enabling Sender-initiated Distributed Applications and
     Checkpointing in Content Centric
     Networks](https://repository.iiitd.edu.in/jspui/bitstream/123456789/336/1/MT13069.pdf),\
     Nitinder Mohan,\
     Master of Technology Thesis, IIIT Delhi (Indraprastha Institute of
     Information Technology), July, 2015\
     [Bibtex](papers/mohan-thesis.bib.html).

124. [Optimizing Checkpoint Restart with Data
     Deduplication](http://downloads.hindawi.com/journals/sp/2016/9315493.pdf),\
     Chen, Zhengyu and Sun, Jianhua and Chen, Hao\
     *Scientific Programming*, May, 2016, Hindawi Publishing
     Corporation\
     [Bibtex](papers/scientific-programming.bib.html).

125. [Transparent Checkpointing for
     Supercomputing](http://mug.mvapich.cse.ohio-state.edu/static/media/mug/presentations/2015/mug15-progress_report_on_transparent_checkpointing_for_supercomputing-jiajun_cao_and_rohan_garg.pdf),\
     Jiajun Cao and Rohan Garg\
     *MVAPICH User Group (MUG\'15)*,\
     Columbus, Ohio, Aug. 20, 2015; [MUG\'15
     program](http://mug.mvapich.cse.ohio-state.edu/mug/15/),
     [slides](http://mug.mvapich.cse.ohio-state.edu/static/media/mug/presentations/2015/mug15-progress_report_on_transparent_checkpointing_for_supercomputing-jiajun_cao_and_rohan_garg.pdf),
     and
     [video](http://mug.mvapich.cse.ohio-state.edu/static/media/mug/presentations/2015/mug15-progress_report_on_transparent_checkpointing_for_supercomputing-jiajun_cao_and_rohan_garg.pdf);\
     [Bibtex](papers/mug15-cao-garg.bib.html).

126. [Transparent Checkpoint-Restart: Re-Thinking the HPC
     Environment](http://mug.mvapich.cse.ohio-state.edu/static/media/mug/presentations/2015/mug15-transparent_checkpoint-restart:_re-thinking_the_hpc_environment-gene_cooperman.pdf),\
     Gene Cooperman,\
     *MVAPICH User Group (MUG\'15)*,\
     Columbus, Ohio, Aug. 19, 2015; [MUG\'15
     program](http://mug.mvapich.cse.ohio-state.edu/mug/15/),
     [slides](http://mug.mvapich.cse.ohio-state.edu/static/media/mug/presentations/2015/mug15-transparent_checkpoint-restart:_re-thinking_the_hpc_environment-gene_cooperman.pdf),
     and
     [video](http://mug.mvapich.cse.ohio-state.edu/static/media/mug/presentations/2015/mug15-transparent_checkpoint-restart:_re-thinking_the_hpc_environment-gene_cooperman.pdf);\
     [Bibtex](papers/mug15-cooperman.bib).

127. [Recent Trends towards Green Clouds by using Fuzzy based Live
     Migration](http://research.ijcaonline.org/volume113/number3/pxc3901597.pdf)
     (or
     [alt](http://search.proquest.com/openview/083ecb9b4f237af323adcb9501b7bb5d/1)),\
     Amrinder Kaur and Anil Kumar,\
     *International Journal of Computer Applications* **113**(3)
     (0975\--8887), pp. 17\--22, Mar., 2015,\
     [Bibtex](papers/ijca15.bib.html).

128. [Power-Check: An Energy-Efficient Checkpointing Framework for HPC
     Clusters](http://ieeexplore.ieee.org/xpl/articleDetails.jsp?tp=&arnumber=7152492),\
     R.R.Chandrasekar, A. Venkatesh, K. Hamidouche and D.K. Panda,\
     *Proc. of 15th IEEE/ACM Int. Symp. on Cluster, Cloud and Grid
     Computing (CCGrid\'15)*,\
     pp. 261\--270, IEEE Press, 2015,
     [Bibtex](papers/ccgrid15power-check.bib.html).

129. [Checkpointing as a Service in Heterogeneous Cloud
     Environments](http://www.ccs.neu.edu/home/gene/papers/ccgrid15.pdf),\
     Jiajun Cao, Matthieu Simonin, Gene Cooperman and Christine Morin,\
     *Proc. of 15th IEEE/ACM Int. Symp. on Cluster, Cloud and Grid
     Computing (CCGrid\'15)*,\
     pp. 61\--70, IEEE Press, 2015,
     [Bibtex](papers/ccgrid15-ckpt-service.bib).

130. [Energy Efficient Rescheduling Algorithm for High Performance
     Computing](http://ieeexplore.ieee.org/xpl/login.jsp?tp=&arnumber=7084521),\
     Manisha Chauhan, Nazia Parveen, Sumit Kumar Saurav and GL, Ganga
     Prasad,\
     *Nat. Conf. on Parallel Computing Technologies (PARCOMPTECH\'15)*,
     IEEE Press, 2015,\
     [Bibtex](papers/parcomptech15.bib.html).

131. [CCNCheck: Enabling Checkpointed Distributed Applications in
     Content Centric Networks](http://arxiv.org/abs/1506.00391),\
     Nitinder Mohan and Pushpendra Singh,\
     *CCNxCon\'15: Content Centric Networking* (technical talk
     abstract), 2 pages,\
     [Bibtex](papers/ccnxcon15.bib.html).

132. [DMTCP: Bringing Interactive Checkpoint-Restart to
     Python](http://iopscience.iop.org/1749-4699/8/1/014005/),\
     Kapil Arya and Gene Cooperman,\
     *Computational Science & Discovery*, 16 pages, 2015, IOPScience,\
     [Bibtex](papers/comp-sci-disc15.bib.html).

133. [Using Checkpointing and Virtualization for Fault
     Injection](http://www.ijnc.org/index.php/ijnc/article/view/112),\
     Cyrille Artho and Kuniyasu Suzaki and Masami Hagiya and Watcharin
     Leungwattanakit and Richard Potter and Eric Platon and Yoshinori
     Tanabe and Franz Weitl and Mitsuharu Yamamoto,\
     *International Journal of Networking and Computing **5**(2)*,
     pp. 347\--372, 2015,\
     [Bibtex](papers/ijnc15.bib.html).

134. [Using Checkpointing and Virtualization for Fault
     Injection](http://ieeexplore.ieee.org/xpl/login.jsp?tp=&arnumber=7052174),\
     Cyrille Artho, Masami Hagiya, Watcharin Leungwattanakit, Eric
     Platon, Richard Potter, Kuniyasu Suzaki, Yoshinori Tanabe, Franz
     Weitl and Mitsuharu Yamamoto,\
     *Second Int. Symp. on Computing and Networking (CANDAR\'14)*,
     pp. 144\--150, Dec., 2014, IEEE Press,\
     [Bibtex](papers/candar14.bib.html).

135. [Be Kind, Rewind \-\-- Checkpoint & Restore Capability for
     Improving Reliability of Large-scale Semiconductor
     Design](http://www.ieee-hpec.org/2014/CD/index_htm_files/FinalPapers/34.pdf),\
     Igor Ljubuncic, Ravi Giri, Avikam Rozenfeld, and Andrew Goldis,\
     *2014 IEEE High Performance Extreme Computing Conference
     (HPEC-2014)*,\
     6 pages, IEEE Press, Sept., 2014,\
     [Bibtex](papers/hpec14.bib.html).

136. [Performance Evaluation of Checkpoint/Restart Techniques: For MPI
     Applications on Amazon
     Cloud](http://ieeexplore.ieee.org/xpl/login.jsp?tp=&arnumber=7036677),\
     Basma Abdel Azeem and Manal Helal,\
     *Informatics and Systems, 9th Int. Conf. on (INFOS\'14)*,
     pp. 49\--57, Sep., 2014, IEEE Press,\
     [Bibtex](papers/infos14.bib.html)

137. [DMTCP: System-Level Checkpoint-Restart in
     User-Space](https://www.youtube.com/watch?v=UeIsZTjVPAI),\
     Kapil Arya and Gene Cooperman,\
     *MVAPICH User Group (MUG\'14)*,\
     Columbus, Ohio, Aug. 26, 2014; [MUG\'14
     program](http://mug.mvapich.cse.ohio-state.edu/mug/14/),
     [slides](http://mug.mvapich.cse.ohio-state.edu/static/media/mug/presentations/2014/cooperman.pdf),
     and [video](https://www.youtube.com/watch?v=UeIsZTjVPAI);\
     [Bibtex](papers/mug14.bib.html).

138. [Metodología para Predecir el Consumo Energético de Checkpoints en
     Sistemas de HPC](http://sedici.unlp.edu.ar/handle/10915/42391),\
     Javier Balladini, Marina Morán, Dolores Rexachs and Emilio Luque,\
     *XX Congreso Argentino de Ciencias de la Computación
     (CACCIC\'14)*,\
     10 pages, Oct., 2014, [Bibtex](papers/caccic14.bib.html).

139. [Using SAGA and the Open Science Grid to Search for
     Aptamers](http://dl.acm.org/citation.cfm?id=2616517),\
     Kevin Shieh, Pilib Ó Broin, David Rhee, Matthew Levy, and Aaron
     Golden,\
     *Proc. of 2014 Ann. Conf. on Extreme Science and Engineering
     Discovery Environment (XSEDE\'14)*,  Art. No. 27, Jul., 2014\
     [Bibtex](papers/xsede14.bib).

140. [Simulation Speedup of ns-3 using Checkpoint and Restore
     (WNS3\'14)](http://dl.acm.org/citation.cfm?id=2630784),\
     Kyle Harrigan and George Riley,\
     *Proceedings of the 2014 Workshop on ns-3 (WNS3\'14)*,  Art. No. 7,
     2014\
     [Bibtex](papers/wns3-14.bib).

141. [User-Space Process Virtualization in the Context of
     Checkpoint-Restart and Virtual
     Machines](http://hdl.handle.net/2047/d20005096),\
     Kapil Arya, PhD thesis, Northeastern University, August, 2014,\
     [Bibtex](papers/aryathesis14.bib).

142. [Use of Checkpoint-Restart for Complex HEP Software on Traditional
     Architectures and Intel
     MIC](http://iopscience.iop.org/1742-6596/523/1/012015),\
     Kapil Arya, Gene Cooperman, Andrea Dotti and Peter Elmer,\
     *J. Physics: Conference Series* **523**, Conference 1,\
     (from Proc. of 15th Int. Workshop on Advanced Computing and
     Analysis Techniques in Physics Research (ACAT2013)),\
     IOPScience, 8 pages, 2014, [Bibtex](papers/acat13.bib.html).

143. [GemFI: A Fault Injection Tool for Studying the Behavior of
     Applications on Unreliable
     Substrates](http://ieeexplore.ieee.org/xpl/articleDetails.jsp?arnumber=6903616),\
     K. Parasyris, S.Tziantzoulis ; C.D. Antonopoulos, and N. Bellas,\
     *44th Ann. IEEE/IFIP Int. Conf. on Dependable Systems and Networks
     (DSN)*, pp. 622\--629 , IEEE Press, Jun., 2014,\
     [Bibtex](papers/dsn14.bib).

144. [Алгоритмы отказоустойчивого управления ресурсами
     пространственно-распределённых вычислительных
     систем](http://vestnik.sibsutis.ru/uploads/1418787713_6329.pdf)\
     (Algorithms for Failover Resource Management in Distributed
     Computing Systems),\
     А.Ю. Поляков , О.В. Молдованова, А.А. Пазников , М.Г. Курносов ,
     С.Н. Мамойленко, А.В. Ефимов, (A. Yu. Polyakov et al.),\
     Vestnik SibGUTIS **11**(4), (УДК 004.382.2) pp. 11\--29, 2014,\
     [Bibtex](papers/vestnik-sibguti14.bib.html).\

145. [Optimization Tools of Parallel Simulation of Nanostructures with
     Quantum
     Dots](http://link.springer.com/article/10.3103/S8756699014030078),\
     K. V. Pavskii, M. G. Kurnosov, and A. Yu. Polyakov,\
     *Optoelectronics, Instrumentation and Data Processing* **50**(3),
     pp. 260\--265,\
     May, 2014, Springer Press,\
     [Bibtex](papers/opto14.bib.html).\
     (Original Russian Text at: K.V. Pavskii, M.G. Kurnosov, A.Yu.
     Polyakov, 2014, published in Avtometriya, 2014, Vol. 50, No. 3,
     pp.  56\--61.)

146. [Modular Software Model Checking for Distributed
     Systems](http://ieeexplore.ieee.org/xpl/login.jsp?tp=&arnumber=6645368),\
     Leungwattanakit, W., Artho, C., Hagiya, M., Tanabe, Y., Yamamoto,
     M., and Takahashi, K.,\
     *IEEE Trans. on Software Engineering* **40**(5), pp. 483\--501,
     May, 2014, IEEE Press,\
     [Bibtex](papers/softeng14.bib.html)

147. [Designing Scalable and Efficient I/O Middleware for
     Fault-Resilient High-Performance Computing
     Clusters](https://etd.ohiolink.edu/!etd.send_file?accession=osu1417733721),\
     Raghunath Raja Chandraseka, PhD thesis, 2014, The Ohio State
     University,\
     [Bibtex](papers/chandrasekathesis14.bib.html)

148. [Improving the Efficiency of Fuzz Testing Using
     Checkpointing](http://e-collection.library.ethz.ch/view/eth:8582),\
     Erenst-Friedrich Zachow,\
     *Masters Thesis, ETH-Zürich, April 1, 2014*,\
     [Bibtex](papers/ethz14.bib).

149. [Towards an Energy-Efficient Tool for Processing the Big
     Data](http://www.computer.org/csdl/proceedings/ficloud/2014/4357/00/4357a448-abs.html),\
     Eric Renault and Selma Boumerdassi,\
     *2nd International Conference on Future Internet of Things and
     Cloud (FiCloud\'14)*, pp. 448\--452, Aug., 2014, IEEE Press,\
     [Bibtex](papers/ficloud14.bib)

150. [Abstraction Checkpointing Levels: Problems and
     Solutions](http://computingonline.net/index.php/computing/article/view/629),
     Bakhta Meroufel and Ghalem Belalem,\
     *International Journal of Computing* **13**(3), pp. 158\--169,
     2014,\
     [Bibtex](papers/ijc14.bib.html).

151. [Explorations of the Viability of ARM and Xeon Phi for Physics
     Processing](http://iopscience.iop.org/1742-6596/513/5/052008),\
     David Abdurachmanov, Kapil Arya, Josh Bendavid, Tommaso Boccali,
     Gene Cooperman, Andrea Dotti, Peter Elmer, Giulio Eulisse,
     Francesco Giacomini, Christopher D. Jones, Matteo Manzali and
     Shahzad Muzaffar,\
     *J. Physics: Conference Series* **513**, Track 5,\
     (from Proc. of 20th Int. Conf. on Computing in High Energy and
     Nuclear Physics (CHEP13)),\
     IOPScience, 7 pages, 2014, [Bibtex](papers/chep13.bib).

152. [jmodeltest.org: Selection of Nucleotide Substitution Models on the
     Cloud](http://bioinformatics.oxfordjournals.org/content/30/9/1310),\
     Jose Manuel Santorum, Diego Darriba, Guillermo L. Taboada, and
     David Posada,\
     *Bioinformatics* **30**(9),\
     pp. 1310-1311, Oxford Journals, Jan. 21, 2014,\
     [Bibtex](papers/bioinf14.bib).

153. [DMTCP: Bringing Checkpoint-Restart to
     Python](http://conference.scipy.org/proceedings/scipy2013/pdfs/arya.pdf),\
     Kapil Arya and Gene Cooperman, *Proc. of the 12th Python in Science
     Conf. (SciPy 2013)*,\
     6 pages, 2013, [Bibtex](papers/scipy13.bib).

154. [A Framework for an In-depth Comparison of Scale-up and
     Scale-out](http://dl.acm.org/citation.cfm?id=2534654),\
     Michael Sevilla, Ike Nassi, Kleoni Ioannidou, Scott Brandt, and
     Carlos Maltzahn,\
     *Proc. of 2013 Int. Workshop on Data-Intensive Scalable Computing
     Systems (DISCS\'13)*, pp. 13\--18, 2013\
     [Bibtex](papers/discs13.bib.html).

155. [A Tool for Selecting the Right Target Machine for Parallel
     Scientific
     Applications](http://www.sciencedirect.com/science/article/pii/S1877050913004948),\
     Javier Panadero, Alvaro Wong, Dolores Rexachs, and Emilio Luque,\
     *Procedia Computer Science* **18**, pp. 1824\--1833, Elsevier,
     2013,\
     [Bibtex](papers/procedia13.bib).

156. [Formal Mathematics on Display: A Wiki for
     Flyspeck](http://link.springer.com/chapter/10.1007/978-3-642-39320-4_10),\
     Carst Tankink, Cezary Kaliszyk, Josef Urban, and Herman Geuvers,\
     *Intelligent Computer Mathematics*,\
     Lecture Notes in Computer Science Volume, vol. 7961, pp. 152\--167,
     Springer, 2013,\
     [Bibtex](papers/intelcompmath13.bib.html).

157. [Towards Computing as a Utility via Adaptive Middleware: An
     Experiment in Cross-paradigm
     Execution](http://www.worldscientific.com/doi/abs/10.1142/S0129626413400021),\
     Jaroslaw Slawinski and Vaidy Sunderam,\
     *Parallel Processing Letters* **23**(2), 18 pages,\
     World Scientific,  June, 2013,\
     [Bibtex](papers/ppl13.bib.html).

158. [Calculation of the Subgroups of a Trivial-Fitting
     Group](http://dl.acm.org/citation.cfm?id=2465525),\
     Alexander J. Hulpke,\
     *Proc. of 38th Int. Symp. on Symbolic and Algebraic Computation*,
     pp. 205\--210, 2013, ACM Press,\
     [Bibtex](papers/issac13.bib).

159. [Semi-Automated Debugging via Binary Search through a Process
     Lifetime](http://www.ccs.neu.edu/home/gene/papers/plos13.pdf),\
     Kapil Arya, Tyler Denniston, Ana-Maria Visan, and Gene Cooperman,\
     *Proc. of 7th Workshop on Programming Languages and Operating
     Systems (PLOS)* (part of Proc. of 24th ACM Symp. on Operating
     System Principles (SOSP)), 2013,\
     ACM Press, Oct., 2013, [Bibtex](papers/plos13.bib.html).

160. [Shorten Device Boot Time for Automotive IVI and Navigation Systems
     (slides)](http://events.linuxfoundation.org/sites/events/files/als13_huang.pdf),\
     Jim Huang and Shi-Wu Lo (developers, 0xlab),\
     *Automotive Linux Summit (ALS2013)*, May 28, 2013.\
     (See \"Part II: Userspace solution: Checkpointing\"; begins at
     slide 66)

161. [SweeD: Likelihood-Based Detection of Selective Sweeps in Thousands
     of
     Genomes](http://sco.h-its.org/exelixis/pubs/Exelixis-RRDR-2013-1.pdf),\
     P. Pavlidis, D. Živkovic, A. Stamatakis, N. Alachiotis and P.
     Pavlidi,\
     Heidelberg Institute for Theoretical Studies, Technical report
     Exelixis-RRDR-2013-1, February, 2013 \`

162. [A Survey of Fault Tolerance Mechanisms and Checkpoint/Restart
     Implementations for High Performance Computing
     Systems](http://link.springer.com/article/10.1007/s11227-013-0884-0),\
     I.P. Egwutuoha, D. Levy, B. Selic and S. Chen,\
     The Journal of Supercomputing, Feb., 2013, Springer

163. [Proposal of Incremental Software Simulation for Reduction of
     Evaluation
     Time](http://ieeexplore.ieee.org/xpls/abs_all.jsp?arnumber=6424584),\
     Atsushi Shina, Kanemitsu Ootsu, Takeshi Ohkawa, Takashi Yokota and
     Takanobu Baba,\
     *Third Int. Conf. on Networking and Computing (ICNC)*,
     pp. 311\--315, IEEE Press, Dec., 2012,
     [Bibtex](papers/icnc12.bib.html).

164. [Implement Checkpointing for Android (to speed up boot time and
     development
     process)](http://elinux.org/images/1/1c/Implement_Checkpointing_for_Android.pdf)
     (slides),\
     Jim Huang and Kito Cheng (developers, 0xlab),\
     *Embedded Linux Conference Europe (ELCE2012)*,\
     Barcelona, Spain; Nov. 5\--7, 2012.
     [Bibtex](papers/elce12.bib.html).

165. [Towards Fault-tolerant Energy-efficient High Performance Computing
     in the
     Cloud](http://ieeexplore.ieee.org/xpl/articleDetails.jsp?tp=&arnumber=6337837),\
     Kurt L. Keville, Rohan Garg, David J. Yates and Kaply Arya and Gene
     Cooperman,\
     *Proc. of 2012 IEEE Computer Society International Conference on
     Cluster Computing*. pp. 622\--626, 2012,
     [Bibtex](https://dmtcp.sourceforge.io/cluster12.bib).

166. [Adapting MPI to MapReduce PaaS Clouds: An Experiment in
     Cross-Paradigm
     Execution](http://dl.acm.org/citation.cfm?id=2415723),\
     Jaroslaw Slawinski and Vaidy Sunderam,\
     *Proc. of 2012 IEEE/ACM Fifth Int. Conf. on Utility and Cloud
     Computing (UCC \'12)*, pp. 199\--203, 2012,
     [Bibtex](https://dmtcp.sourceforge.io/papers/ucc12.bib).

167. [Creating and Improving Multi-Threaded
     Geant4](http://iopscience.iop.org/1742-6596/396/5/052029).\
     Xin Dong, Gene Cooperman, John Apostolakis, Sverre Jarp, Andrzej
     Nowak, Makoto Asai and Daniel Brandt,\
     *Journal of Physics: Conference Series*, Volume **396**, Part 5,
     2012

168. [Temporal Meta-Programming: Treating Time as a Spatial
     Dimension](http://hdl.handle.net/2047/d20002935),\
     Ana-Maria Visan, PhD thesis, Northeastern University, April, 2012,
     [Bibtex](papers/visanthesis12.bib.html).

169. [Verification of Embedded Control Systems by Simulation and Program
     Execution
     Control](http://ieeexplore.ieee.org/xpls/abs_all.jsp?arnumber=6315536),\
     Stefan Resmerita and Wolfgang Pree,\
     *American Control Conference (ACC)*, pp. 3581\--3586, June, 2012,
     IEEE Press, [Bibtex](papers/acc12.bib.html)

170. [Checkpointing in Distributed Heterogeneous
     Environments](https://coconucos.cs.uni-duesseldorf.de/forschung/pubs/2012/Report2012_GCP.pdf),\
     Michael Schöttner and John Mehnert-Spahn,\
     Technical Report, Heinrich Heine University, Duesseldorf, Germany,
     26 pages, March, 2012,\
     (from [Universität Düsseldorf:
     Publications](http://www.cs.hhu.de/en/research-groups/operating-systems/publications.html)),\
     [Bibtex](papers/uniduess12.bib.html).

171. [Source-Level Transformation of Legacy Sequential Program into
     Scalable Thread-Parallel
     Code](http://dl.acm.org/citation.cfm?id=2522173),\
     Xin Dong, PhD thesis, Northeastern University, Dec., 2011,
     [Bibtex](papers/xindongthesis11.bib.html).

172. [Model Checking Distributed Systems by Combining Caching and
     Process
     Checkpointing](http://staff.aist.go.jp/c.artho/papers/checkpointing.pdf),\
     Watcharin Leungwattanakit, Cyrille Artho, Masami Hagiya, Yoshinori
     Tanabe, and Mitsuharu Yamamoto,\
     *26th IEEE/ACM International Conference on Automated Software
     Engineering (ASE)*, pp. 103\--112,\
     IEEE Press, Dec., 2011. [Bibtex](papers/ase11.bib.html).

173. [Including the Workload Effect in the Parallel Program
     Signature](http://ieeexplore.ieee.org/xpl/freeabs_all.jsp?arnumber=6063006),\
     J.M. Canillas, A. Wong, D. Rexachs, and E. Luque,\
     *Proc. of 13th Int. Conf. on High Performance Computing and
     Communications (HPCC)*, pp. 304\--311,\
     IEEE Computer Society, Sept., 2011. [Bibtex](papers/hpcc11.bib).

174. [Predicting Parallel Applications Performance Using Signatures: the
     Workload
     Effect](http://ieeexplore.ieee.org/xpl/freeabs_all.jsp?arnumber=6126624),\
     J.M. Canillas, A. Wong, D. Rexachs, and E. Luque,\
     *9th IEEE/ACS International Conference on Computer Systems and
     Applications (AICCSA)*, pp. 299\--300,\
     IEEE Computer Society, Dec., 2011. [Bibtex](papers/aiccsa11.bib).

175. [URDB: A Universal Reversible Debugger Based on Decomposing
     Debugging
     Histories](http://www.ccs.neu.edu/home/gene/papers/plos11.pdf),\
     Ana-Maria Visan, Kapil Arya, Gene Cooperman, and Tyler Denniston,\
     *Proc. of 6th Workshop on Programming Languages and Operating
     Systems (PLOS)* (part of Proc. of 23rd ACM Symp. on Operating
     System Principles (SOSP)), 2011,\
     ACM Press, Oct., 2011. [Bibtex](papers/plos11.bib.html).

176. [Direct Inference of Protein\--DNA Interactions using Compressed
     Sensing Methods](http://www.pnas.org/content/108/36/14819),\
     Mohammed AlQuraishi and Harley H. McAdams,\
     *Proc. of National Academy of Sciences (PNAS)* **108**(36),
     pp. 14819\--14824,\
     Sept. 6, 2011. [Full Text
     (html)](http://www.pnas.org/content/108/36/14819.full), [Full Text
     (pdf)](http://www.pnas.org/content/108/36/14819.full.pdf+html),
     [Bibtex](papers/pnas11.bib.html).

177. [Hiroyuki Takizawa and Kentaro Koyama and Katsuto Sato and Kazuhiko
     Komatsu and Hiroaki
     Kobayashi](http://www.sc.isc.tohoku.ac.jp/~tacky/papers/htakizawa_ipdps2011.pdf),\
     CheCL: Transparent Checkpointing and Process Migration of OpenCL
     Applications,\
     *Proc. of 2011 IEEE International Parallel and Distributed
     Processing Symposium*, pp. 864\--876\
     IEEE Computer Society, May, 2011. [Bibtex](papers/ipdps11.bib).

178. [Distributed Speculative Parallelization using Checkpoint
     Restart](http://www.sciencedirect.com/science/article/pii/S1877050911001025),\
     Devarshi Ghoshal, Sreesudhan R. Ramkumar, and Arun Chauhan,\
     *Procedia Computer Science*, **4**, pp. 422\--431,\
     May, 2011,
     [Slides](http://www.cs.indiana.edu/~achauhan/Teaching/B649/2011-Fall/StudentPresns/speculative.pdf),
     [Bibtex](papers/procedia-cs11.bib.html).

179. [Unibus: Aspects of Heterogeneity and Fault Tolerance in Cloud
     Computing](http://ieeexplore.ieee.org/xpl/freeabs_all.jsp?arnumber=5470876) M.
     Slawiñska, J. Slawinski, and V. Sunderam,\
     *Proc. of IEEE Int. Symp. on Parallel & Distributed Processing,
     Workshops and PhD Forum (IPDPSW)*, pp. 1\--10,\
     Apr., 2010, [Bibtex](papers/ipdpsw11.bib.html).

------------------------------------------------------------------------

Click [here for comments.](contactUs.html){.sidebar}

[![SourceForge.net
Logo](http://sourceforge.net/sflogo.php?group_id=96405&type=5){border="0"
height="62" width="210"}](http://sourceforge.net)
:::
