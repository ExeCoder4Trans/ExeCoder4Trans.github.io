---
layout: project_page
permalink: /

title: "ExeCoder: Empowering Large Language Models with Executability Representation for Code Translation"

authors: |
    Minghua He<sup>1</sup>*, Fangkai Yang<sup>2</sup>, Pu Zhao<sup>2</sup>, Wenjie Yin<sup>3</sup>, Yu Kang<sup>2</sup>, Qingwei Lin<sup>2</sup>, Saravan Rajmohan<sup>2</sup>, Dongmei Zhang<sup>2</sup>, Qi Zhang<sup>2</sup>

affiliations: |
    <sup>1</sup> Peking University, China<br>
    <sup>2</sup> Microsoft, China<br>
    <sup>3</sup> KTH Royal Institute of Technology, Sweden

notes: |
    * Work is done during an internship at Microsoft.

contact: |
    hemh2120@stu.pku.edu.cn

paper: |
    https://arxiv.org/abs/2501.18460

code: |
    https://github.com/Microsoft/ExeCoder
# video: |
#     https://youtu.be/IFFLb5mgzY0
---

<!-- 
# paper: https://www.cs.virginia.edu/~robins/Turing_Paper_1936.pdf
#  <span>^1^Microsoft,</span> <span>^2^Institute of Automation, Chinese Academy of Sciences,</span> <span>^3^School of Artificial Intelligence, University of Chinese Academy of Sciences,</span>
    # Microsoft
    # Institute of Automation, Chinese Academy of Sciences
    # School of Artificial Intelligence, University of Chinese Academy of Sciences
# paper: 'coming soon'
# video: https://www.youtube.com/results?search_query=turing+machine
# code: 'coming soon'
# data: https://huggingface.co/docs/datasets
 -->

<!-- <video width="100%" height="auto" controls>
  <source src="{{ site.baseurl }}/static/video/AutoRAG.mp4" type="video/mp4">
</video> -->

---

<!-- Using HTML to center the abstract -->
<div class="columns is-centered has-text-centered">
    <div class="column is-four-fifths">
        <h2>Abstract</h2>
        <div class="content has-text-justified">
Code translation is a crucial activity in the software development and maintenance process, and researchers have recently begun to focus on using pre-trained large language models (LLMs) for code translation. However, existing LLMs only learn the contextual semantics of code during pre-training, neglecting executability information closely related to the execution state of the code, which results in unguaranteed code executability and unreliable automated code translation. To address this issue, we propose ExeCoder, an LLM specifically designed for code translation, aimed at utilizing executability representations such as functional semantics, syntax structures, and variable dependencies to enhance the capabilities of LLMs in code translation. To evaluate the effectiveness of ExeCoder, we manually enhanced the widely used benchmark TransCoder-test, resulting in a benchmark called TransCoder-test-X that serves LLMs. Evaluation of TransCoder-test-X indicates that ExeCoder achieves state-of-the-art performance in code translation, surpassing existing open-source code LLMs by over 10.88% to 38.78% and over 27.44% to 42.97% on two metrics, and even outperforms the renowned closed-source LLM GPT-4o.
        </div>
    </div>
</div>



<!-- > Note: This is an example of a Jekyll-based project website template: [Github link](https://github.com/shunzh/project_website).\
> The following content is generated by ChatGPT. The figure is manually added. -->

## Key Contributions
1. We developed ExeCoder, a LLM specifically designed for code translation, which significantly outperforms all other open-source code LLMs, achieving SOTA performance. Notably, the ExeCoder surpasses well-known the renowned closed-source LLM GPT-4o.

2.  We propose a Progressive Executability Representation Learning strategy that aligns with the learning theory of programming experts and effectively learns executability representations of code.

3. We enhanced the widely used code translation benchmark, TransCoder-test, resulting in a new benchmark called TransCoder-test-X, which is capable of evaluating the code translation abilities of LLMs.

4. We conducted a preliminary study that emphasizes the critical role of executability representations of code in achieving excellent code translation performance.

## Main Ideas
<div align="center">
    <img src= "{{ site.baseurl }}/static/image/teaser.png" alt="Hierarchical UCB" style="width: 60%;">
    <p><em>Figure 1: Executability Representation for Code Translation. Existing models simply copy variable name from the source code, ignoring conflicts with called built-in function, which leads to TypeError exception. The model that considers code executability learn the syntactic structure of source code and avoid call conflicts through explicit loop summation.</em></p>
</div>

<br><br> <!-- Adding two extra empty lines -->

<div align="center">
    <img src= "{{ site.baseurl }}/static/image/pipeline.png" alt="Hierarchical UCB" style="width: 150%; display: block; margin-left: auto; margin-right: auto;">
    <p><em>Figure 2: The ExeCoder's pipeline. The ExeCoder first utilizes a text that describes the code functionality to encode functional semantic information. Subsequently, the ExeCoder uses an abstract syntax tree (AST) to encode the syntactic structure information. The AST has proven effective in encoding both lexical and syntactic information. Finally, the ExeCoder employs a data flow graph (DFG) to encode the variable dependency information. The DFG tracks the data dependency relationships between variables. With the benefit of the well-designed Progressive Executability Representation Learning (PERL) strategy, the ExeCoder can fully leverage the progressively refined code executability representation to enhance the cross-programming language understanding capabilities of LLMs.</em></p>
</div>

<br><br> <!-- Adding two extra empty lines -->

<div align="center">
    <img src= "{{ site.baseurl }}/static/image/case.png" alt="Hierarchical UCB" style="width: 150%; display: block; margin-left: auto; margin-right: auto;">
    <p><em>Figure 3: Three types of Executability Representations. The first example illustrates an error related to functional semantic, where the baseline model is not informed of the function's role in obtaining the minimum number, substituting a similar modulus symbol for the division operator. The second example highlights an error in syntactic structure, where the baseline model uses forced type conversion to convert characters to numbers, which raises a ValueError exception when non-numeric characters are included in the input. The third example presents an error regarding variable dependency, where the baseline model has not learned the transmission of variables, thereby neglecting to create a concatenation of string with itself. These errors result in a minimal edit distance but have a significant impact on the execution. Learning the executability representation can indicate the execution status, aiding in resolving these issues.</em></p>
</div>

<!-- ## Table: Comparison of Computable and Non-Computable Numbers

| Computable Numbers | Non-Computable Numbers |
|-------------------|-----------------------|
| Rational numbers, e.g., 1/2, 3/4 | Transcendental numbers, e.g., π, e |
| Algebraic numbers, e.g., √2, ∛3 | Non-algebraic numbers, e.g., √2 + √3 |
| Numbers with finite decimal representations | Numbers with infinite, non-repeating decimal representations |

He used the concept of a universal Turing machine to prove that the set of computable functions is recursively enumerable, meaning it can be listed by an algorithm. -->
<!-- 
## Significance
Turing's paper laid the foundation for the theory of computation and had a profound impact on the development of computer science. The Turing machine became a fundamental concept in theoretical computer science, serving as a theoretical model for studying the limits and capabilities of computation. Turing's work also influenced the development of programming languages, algorithms, and the design of modern computers. -->

## Citation
```
@misc{he2025execoderempoweringlargelanguage,
      title={ExeCoder: Empowering Large Language Models with Executability Representation for Code Translation}, 
      author={Minghua He and Fangkai Yang and Pu Zhao and Wenjie Yin and Yu Kang and Qingwei Lin and Saravan Rajmohan and Dongmei Zhang and Qi Zhang},
      year={2025},
      eprint={2501.18460},
      archivePrefix={arXiv},
      primaryClass={cs.SE},
      url={https://arxiv.org/abs/2501.18460}, 
}
```