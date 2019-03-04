========================================================================================================================
(IRT和BKT的结合)Learning meets Assessment: On the relation between Item Response Theory and Bayesian Knowledge Tracing
========================================================================================================================

.. warning::
    这篇论文实在是没看懂！！！！！！！


Benjamin Deonovic, Michael Yudelson, Maria Bolsinova, Meirav Attali, and Gunter Maris
October 15, 2018

Abstract
========================
Few models have been more ubiquitous in their respective fields than Bayesian knowledge tracing and item response theory.
Both of these models were developed to analyze data on learners. However, the study designs that these models are designed for differ; Bayesian knowledge tracing is designed to analyze longitudinal data while item response theory is built for cross-sectional data. This paper illustrates a fundamental connection between these two models. Specifically, the stationary distribution of the latent variable and the observed response variable in Bayesian knowledge Tracing are related to an item response theory model. This connection between these two models highlights a key missing component: the role of education in these models.
A research agenda is outlined which answers how to move forward with modeling learner data.

在贝叶斯知识追踪和项目反应理论中，很少有模型在各自的领域中普遍存在。这两个模型都是为了分析学习者的数据而开发的。
然而，该研究设计这些模型的设计不同;贝叶斯知识追踪旨在分析纵向数据，同时为横截面数据建立项目响应理论。
本文阐述了这两种模型之间的基本联系。具体而言，潜在变量的静态分布和贝叶斯知识追踪中观察到的响应变量与项目响应理论模型有关。这两个模型之间的这种联系突出了一个关键的缺失部分：教育在这些模型中的作用。概述了一个研究议程，该议程回答了如何推进学习者数据的建模。

Introduction
========================

Learning and assessment deal with related, yet distinct concepts. Learning can be defined as the acquisition of knowledge, skills, values, beliefs, and habits through experience, study, or instruction. Assessments are instruments designed to observe behavior in a learner and produce data that can be used to draw inference about the knowledge, skills, values, beliefs, and habits that the learner has. Although learning and assessment are both key to education, the statistical models used to describe learning data and assessment data have significantly diverged and grown to leverage the salient features and distinct assumptions that are embodied in their respective data sets. The fields of ed- ucational data mining and learning analytics harness the dynamic, temporal, and large scale nature of learning data to construct models which can be used to predict learner performance, personalize and adapt instructional content, recommend intervention and curriculum changes, and provide information visualization to track progress. On the other hand, the same objectives are targeted by the field of psychometrics, using cross-sectional assessment data rather than longitudinal data. Specifically this paper will explore the connections between Bayesian knowledge Tracing (BKT) and item response theory (IRT). BKT, a statistical model in educational data mining, is the most ubiquitous model used for data obtained from intelligent tutoring systems, which are systems con- structed to provide immediate and customized instruction to learners.
IRT, a modeling framework developed in the field of psychometrics, was designed for constructing and analyzing assessments.

学习和评估涉及相关但不同的概念。学习可以定义为通过经验，学习或指导获取知识，技能，价值观，信仰和习惯。
评估是用于观察学习者行为并生成数据的工具，可用于推断学习者的知识，技能，价值观，信仰和习惯。
虽然学习和评估都是教育的关键，但用于描述学习数据和评估数据的统计模型已显着不同并发展，以利用其各自数据集中体现的显着特征和独特假设。
教育数据挖掘和学习分析领域利用学习数据的动态，时间和大规模性质来构建模型，这些模型可用于预测学习者的表现，个性化和调整教学内容，推荐干预和课程变更，并提供信息可视化以跟踪进度。另一方面，心理测量学领域使用横断面评估数据而不是纵向数据来确定相同的目标。具体来说，本文将探讨贝叶斯知识追踪（BKT）与项目反应理论（IRT）之间的联系。 BKT是教育数据挖掘中的统计模型，是用于从智能辅导系统获得的数据的最普遍的模型，智能辅导系统是为学习者提供即时和定制指导的系统。 IRT是心理测量学领域开发的建模框架，旨在构建和分析评估。


Historically, the research in BKT and IRT models has had little overlap, as on the surface these models seem to be completely different and incompatible.
Both of these models fit their respective data sets well, but each has flaws. Due to the relationship between the longitudinal learning data and the cross-sectional assessment data,
we posit that there exists a relationship between BKT and IRT models. Indeed we will show that there is an intimate connection between these two models that places BKT and IRT under an umbrella of general models of learning and assessment data. First in Section 2 the BKT model is explained in detail and extensions to the standard model that have been described in the literature are also listed. Section 3 describes the IRT model and its extensions. Section 4 discusses the shortcomings of the respective models in the context of learning. Section 5 describes the connection between the BKT models and IRT models and how the shortcomings of each model can be addressed by incorporating concepts from the other.

从历史上看，BKT和IRT模型的研究几乎没有重叠，因为从表面上看，这些模型似乎完全不同且不相容。
这两种模型都很好地适合各自的数据集，但每种模型都有缺陷。
由于纵向学习数据和横断面评估数据之间的关系，我们认为BKT和IRT模型之间存在关联。
事实上，我们将证明这两种模型之间存在密切联系，将BKT和IRT置于学习和评估数据的一般模型的保护之下。
首先在第2节中详细解释了BKT模型，并且还列出了文献中描述的标准模型的扩展。第3节描述了IRT模型及其扩展。
第4节讨论了学习背景下各个模型的缺点。第5节描述了BKT模型和IRT模型之间的联系，以及如何通过合并另一个模型的概念来解决每个模型的缺点。


It should be noted that this paper does not describe a novel statistical model nor an algorithm to fit a statistical model to either the longitudinal learning data or cross-sectional assessment data.
Rather this paper identifies a key theoretical connection between two existing and popular models.
However, this result is not inconsequential.
The connection between BKT and IRT highlights that there is a crucial ingredient missing from both.
That crucial ingredient is education. Only when learning, assessment, and education go hand in hand can there be hope to make progress.
Hence in Section 7 we end this paper with sketching a research agenda for achieving this.

应该注意的是，本文没有描述新的统计模型，也没有描述将统计模型拟合到纵向学习数据或横截面评估数据的算法。
相反，本文确定了两个现有和流行模型之间的关键理论联系。
但是，这个结果并非无关紧要。 BKT与IRT之间的联系凸显出两者都缺少一个至关重要的成分。这个关键因素是教育。只有学习，评估和教育齐头并进，才有希望取得进步。
因此，在第7节中，我们结束本文，草拟了实现这一目标的研究议程。

BKT
==================

Bayesian Knowledge Tracing or BKT (Corbett and Anderson, 1995) is a modeling paradigm frequently used in the field of Intelligent Tutoring Systems (ITS) where it is tasked with continuously tracking the process of student knowledge acquisition and serves as the basis for selecting the next problem set or skill that a student should work on,
once mastery has been attained on the current problem set or skill.
In BKT, skills are modeled as (latent) binary variables (mastered/not-mastered) and learning is characterized as a transition between these states.
Let :math:`Z_{pkt}` denote the dichotomous state (i.e. mastery/not-mastery) of the kth skill for the pth person at attempt t for k = 1,...,K, p = 1,...,n and t = 1, . . . , :math:`T_p` .
Originally, BKT was developed with cognitive theory of learning in mind.
Each model addresses one skill and assumes that it is relatively fine-grained (e.g., addition, subtraction, division) (Corbett and Anderson, 1995).
Granularity of the skills is a subject of experimental research and, for example,
‘addition’ could be split to ’single-digit addition’ and ’multi-digit addition’ if the data indicates the split is warranted (Koedinger et al, 2013).


贝叶斯知识追踪或BKT（Corbett和Anderson，1995）是一种在智能辅导系统（ITS）领域经常使用的建模范例，其任务是不断跟踪学生知识获取的过程，
并作为选择下一个的基础。一旦掌握了当前的问题集或技能，学生应该处理的问题集或技能。在BKT中，技能被建模为（潜在的）二进制变量（掌握/未掌握），
并且学习被表征为这些状态之间的过渡。设 :math:`Z_{pkt}` 表示对于k = 1，...，K，p = 1，...，n和t = 1，在尝试t时第p个人的第k个技能的二分状态（即掌握/不掌握）， 。 。 。 ，Tp。
最初，BKT是在学习认知理论的基础上发展起来的。
每个模型都针对一种技能，并假设它是相对细粒度的（例如，加法，减法，除法）（Corbett和Anderson，1995）。
技能的粒度是实验研究的主题，例如，如果数据表明分裂是有必要的话，“加法”可以分为“单位数添加”和“多位数添加”（Koedinger等，2013） 。