# Balancing Large-scale Relevance Judgement Collections for Fair Neural Ranking
This repository contains the code and resources for our proposed approach to create a balanced relevance-judgment collection that diminishes the bias conveyed to neural rankers. The main focus of this approach is to propose an automated method to generate pairs of query and relevant documents that have controlled degrees of bias. Figure below shows our proposed methodology.

<p align="center">
  <img src="https://github.com/balancedbias/debiasingneuralrankers/blob/89eb6e9a8abedf53ba5f387300175558dae38f60/Methodology.png">
</p>

As you can see, Table 1 shows some examples of balanced query-document pairs. In this table each female and male document-pairs share similar level of psychological characteristics in their passages.
#### Table 1: Examples of paired gendered queries in our generated dataset
<table class="tg">
<thead>
  <tr>
    <th class="tg-1wig">Examples</th>
    <th class="tg-1wig"><span style="font-style:normal;text-decoration:none;color:#000;background-color:transparent">Gender Affiliation</span></th>
    <th class="tg-1wig"><span style="font-style:normal;text-decoration:none;color:#000;background-color:transparent">Generated Query</span></th>
    <th class="tg-1wig"><span style="font-style:normal;text-decoration:none;color:#000;background-color:transparent">Source Passage</span></th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Sample Pair 1</span></td>
    <td class="tg-0lax"><span style="font-style:normal;text-decoration:none;color:#000;background-color:transparent">Male</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">male sex hormones</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">In the male, the principal sex hormones are the androgens, of which  testosterone is the most important. The androgens are steroid  hormones produced mainly by the Leydig cells(interstitial cells  located near the seminiferous tubules) of the Testes.</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-style:normal;text-decoration:none;color:#000;background-color:transparent">Female</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">which hormone is required to regulate uterine cycle</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">The regulation of both the ovarian and uterine cycles is the function of several gonadotropic and ovarian hormones. Among the most important of the gonadotropins are luteinizing hormone (LH) and follicle stimulating hormone (FSH), while the most crucial ovarian hormones are the androgens, estrogen and progesterone.</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Sample Pair 2</span></td>
    <td class="tg-0lax"><span style="font-style:normal;text-decoration:none;color:#000;background-color:transparent">Male</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">when to stop getting acne in boys</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Boys start to get acne at the age of approximately 12 years, with a range of 9 to 15 years old. As most girls will attest, boys on average mature later than girls. Early on in the onset of teen acne, the main lesions are blackheads and whiteheads.</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-style:normal;text-decoration:none;color:#000;background-color:transparent">Female</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">how long before you can get pregnant</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Most couples can conceive in about a three month period of time. The factors that can slow down the process include older age, medical conditions or lifestyle habits that reduce fertility. Here is the average conception times: 30% of couples get pregnant in one menstrual cycle.</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Sample Pair 3</span></td>
    <td class="tg-0lax"><span style="font-style:normal;text-decoration:none;color:#000;background-color:transparent">Male</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">average height of an adult male</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">The average height for the adult male is roughly 5'9 historically. The tallest man recorded being around 8'11 tall, and the shortest being around 1'10.5. A chart outlining average male heights around the world is illustrated in the following table.</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-style:normal;text-decoration:none;color:#000;background-color:transparent">Female</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">average height female</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">The average female height is roughly 5'4 historically-the tallest woman being 7'7.5 tall.A chart outlining average female heights around the world is illustrated in the following table average Male Height. The average height for the adult male is roughly 5'9 historically. The tallest man recorded being around 8'11 tall, and the shortest being around 1'10.5 (who is also the shortest known adult human).</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Sample Pair 4</span></td>
    <td class="tg-0lax"><span style="font-style:normal;text-decoration:none;color:#000;background-color:transparent">Male</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">vess carlos worth</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">$15 Million. Bryan Baeumler net worth: Brian Baeumler is a Canadian entrepreneur and TV star who has net worth of $15 million dollars.</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-style:normal;text-decoration:none;color:#000;background-color:transparent">Female</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">lesley stahl net worth</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Lesley Stahl net worth: Lesley Stahl is an American television journalist who has a net worth of $20 million dollars.Lesley Stahl was born in Lynn, Massachusetts, and went on to graduate from Wheaton College.esley Stahl net worth: Lesley Stahl is an American television journalist who has a net worth of $20 million dollars.</span></td>
  </tr>
 <tr>
    <td class="tg-0lax" rowspan="2"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Sample Pair 5</span></td>
    <td class="tg-0lax"><span style="font-style:normal;text-decoration:none;color:#000;background-color:transparent">Male</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">can radiation help with prostate cancer</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">As with most prostate cancer treatments, external beam radiation therapy can also cause side effects. The severity can depend on the type of radiation, dose size, length of treatment and area of treatments.</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-style:normal;text-decoration:none;color:#000;background-color:transparent">Female</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">does dhea help estrogen</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Combining DHEA and estrogen might cause symptoms of excess estrogen, such as nausea, headache and insomnia. Lithium. Use of DHEA with lithium might reduce the drug's effectiveness.</span></td>
  </tr>
</tbody>
</table>

## Utility
We now show how combining our proposed query-document pairs with existing gold standard relevance judgement datasets can lead to the training of less biased neural rankers that have competitive retrieval effectiveness. For this purpose, we augment the small training set of MS MARCO with data from our generated query-document pairs using different ratios with 10% increments. For instance, a 15% ratio would mean that we augment the MS MARCO training set with an additional n query-document pairs from our dataset where n is equivalent to 15% of the size of the MS MARCO small training set. Based on the de-biased datasets, we leverage the BERT-base-uncased transformer model for passage ranking  and train it on the original dataset, i.e., the small training set of MS MARCO, as well as the newly developed de-biased datasets and compare their effectiveness in Table 2.

#### Table 2: Model effectiveness on de-biased datasets. * indicates statistically significant decrease in effectiveness.
<table class="tg">
<thead>
  <tr>
    <th class="tg-0lax">Neural Re-ranker Model</th>
    <th class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Training Dataset</span></th>
    <th class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Ratio</span></th>
    <th class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">MRR@10</span></th>
    <th class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">% Reduction</span></th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0lax" rowspan="5">BERT-base-uncased</td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Original Set</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">-</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.3080</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">-</span></td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="4"><br><br><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">De-biased Datasets</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.05</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.3100</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.65%</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.15</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.3039</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">-1.33%</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.25</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.3002</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">-2.53%</span></td>
  </tr>
  <tr>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.35</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.2905</span></td>
    <td class="tg-0lax"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">-5.68%*</span></td>
  </tr>
</tbody>
</table>

## Bias Measurement
In order measure bias we use three widely adopted psychological and stereotypical gender bias measurement methods to show that decrease in bias happens effectively regardless of how gender biases are measured. We adopt two strategies to measure gender biases. The first approach relies on measuring differences observed across pairs of gender-affiliated queries. As you can see in Table 3, when the model is trained on the de-biased dataset, the difference between psychological charactiristics of documents associated with male and female queries has decreased significantly.

#### Table 3: Impact of training on de-biased dataset on the difference in psychological characteristics of gender-affiliated queries.
<table class="tg">
<thead>
  <tr>
    <th class="tg-0lax">Neural Re-ranker Model</th>
    <th class="tg-0pky" colspan="2"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Training Dataset</span></th>
    <th class="tg-fymr"><span style="font-weight:700;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Affective Processes</span></th>
    <th class="tg-fymr"><span style="font-weight:700;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Cognitive Processes</span></th>
    <th class="tg-fymr"><span style="font-weight:700;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Drives</span></th>
    <th class="tg-fymr"><span style="font-weight:700;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Personal Concerns</span></th>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0lax" rowspan="7">BERT-base-uncased</td>
    <td class="tg-c3ow" rowspan="3"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Original Dataset </span></td>
    <td class="tg-0pky"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Female </span><br><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Queries</span> <a href="https://github.com/balancedbias/debiasingneuralrankers/blob/main/results/trec_runs/female_affiliated_queries/bert_base_uncased_original_dataset.trec" target="_top"> (Run)</td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0315</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0725</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0545</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0600</span></td>
  </tr>
  <tr>
    <td class="tg-0pky"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Male </span><br><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Queries</span> <a href="https://github.com/balancedbias/debiasingneuralrankers/blob/main/results/trec_runs/male_affiliated_queries/bert_base_uncased_original_dataset.trec" target="_top"> (Run)</td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0290</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0521</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0641</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0829</span></td>
  </tr>
  <tr>
    <td class="tg-0pky"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Difference</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0025</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0204</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0095</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0229</span></td>
  </tr>
  <tr>
    <td class="tg-c3ow" rowspan="3"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">De-biased Dataset</span></td>
    <td class="tg-0pky"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Female </span><br><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Queries</span> <a href = https://github.com/balancedbias/debiasingneuralrankers/blob/main/results/trec_runs/female_affiliated_queries/bert_base_uncased_debiased_dataset_0.25.trec" target="_top"> (Run)</td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0304</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0730</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0536</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0546</span></td>
  </tr>
  <tr>
    <td class="tg-0pky"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Male </span><br><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Queries</span> <a href="https://github.com/balancedbias/debiasingneuralrankers/blob/main/results/trec_runs/male_affiliated_queries/bert_base_uncased_debiased_dataset_0.25.trec" target="_top"> (Run)</td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0288</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0563</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0624</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0747</span></td>
  </tr>
  <tr>
    <td class="tg-0pky"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">Difference</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0016</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0167</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0088</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">0.0201</span></td>
  </tr>
  <tr>
    <td class="tg-c3ow" colspan="2"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">%Reduction</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">36.00%</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">18.13%</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">7.37%</span></td>
    <td class="tg-dvpl"><span style="font-weight:400;font-style:normal;text-decoration:none;color:#000;background-color:transparent">12.22%</span></td>
  </tr>
</tbody>
</table>

In the second approach, we adopt another gender bias measurement strategy and use the method proposed by Navid Rekabsaz and LIWC toolkit to calculate bias among the top-10 retreived list of documents for queries and report the results in Table 4. 

#### Table 4: The impact of training BERT-base-uncased on the de-biased dataset on proxy measures of bias based on different neutral query sets.
<table class="tg">
<thead>
  <tr>
    <th class="tg-0lax" rowspan="2">Neural Re-ranker Model</th>
    <th class="tg-0lax" rowspan="2">Query Set</th>
    <th class="tg-0lax" rowspan="2">Training Set</th>
    <th class="tg-0lax" colspan="4">ARaB</th>
    <th class="tg-0lax" colspan="2">LIWC</th>
  </tr>
  <tr>
    <td class="tg-0lax">TF</td>
    <td class="tg-0lax">TF (%)</td>
    <td class="tg-0lax">Boolean</td>
    <td class="tg-0lax">Boolean (%)</td>
    <td class="tg-0lax">Male Female Diff</td>
    <td class="tg-0lax"> Improvement (%)</td>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0lax" rowspan="4">BERT-base-uncased</td>
    <td class="tg-0lax" rowspan="2"><a href="https:https://github.com/navid-rekabsaz/GenderBias_IR/blob/master/resources/queries_gender_annotated.csv" target="_top">1765 Neutral Queries</td>
    <td class="tg-0lax">Original Dataset <a href="https://github.com/balancedbias/debiasingneuralrankers/blob/main/results/trec_runs/1765_neutral_queries/bert_base_uncased_original_dataset.trec" target="_top"> (Run)</td>
    <td class="tg-baqh">0.072</td>
    <td class="tg-baqh">-</td>
    <td class="tg-baqh">0.059</td>
    <td class="tg-baqh">-</td>
    <td class="tg-baqh">0.0117</td>
    <td class="tg-baqh">-</td>
  </tr>
  <tr>
    <td class="tg-0lax">De-biased Dataset <a href="https://github.com/balancedbias/debiasingneuralrankers/blob/main/results/trec_runs/1765_neutral_queries/bert_base_uncased_debiased_dataset_0.25.trec" target="_top"> (Run)</td>
    <td class="tg-baqh">0.059</td>
    <td class="tg-baqh">18.05%</td>
    <td class="tg-baqh">0.049</td>
    <td class="tg-baqh">16.95%</td>
    <td class="tg-baqh">0.0110</td>
    <td class="tg-baqh">5.98%</td>
  </tr>
  <tr>
    <td class="tg-0lax" rowspan="2"><a href="https://github.com/CPJKU/FairnessRetrievalResults/blob/main/resources/fairnesssensitive_queries/msmarco_passage.dev.fair.tsv" target="_top">215 Social Problematic Queries</td>
    <td class="tg-0lax">Original Dataset <a href="https://github.com/balancedbias/debiasingneuralrankers/blob/main/results/trec_runs/215_neutral_queries/bert_base_uncased_original_dataset.trec" target="_top"> (Run)</td>
    <td class="tg-baqh">0.029</td>
    <td class="tg-baqh">-</td>
    <td class="tg-baqh">0.017</td>
    <td class="tg-baqh">-</td>
    <td class="tg-baqh">0.0060</td>
    <td class="tg-baqh">-</td>
  </tr>
  <tr>
    <td class="tg-0lax">De-biased Dataset <a href="https://github.com/balancedbias/debiasingneuralrankers/blob/main/results/trec_runs/215_neutral_queries/bert_base_uncased_debiased_dataset_0.25.trec" target="_top"> (Run)</td>
    <td class="tg-baqh">0.019</td>
    <td class="tg-baqh">34.48%</td>
    <td class="tg-baqh">0.011</td>
    <td class="tg-baqh">35.29%</td>
    <td class="tg-baqh">0.0057</td>
    <td class="tg-baqh">16.67%</td>
  </tr>
</tbody>
</table>

We further compare our work with the state of the art method that proposes an adversarial approach to reduce bias in neural rankers, known as [ADVBERT](https://arxiv.org/pdf/2104.13640.pdf). As suggested in their paper, we adopt the BERT-tiny model and train it based on the adversarial method proposed by the authors over the original MS MARCO dataset. We additionally, train the same BERT-tiny model without adversarial training on the original MS MARCO dataset as well as our proposed de-biased dataset. In Table 5, we compare the retrieval effectiveness and proxy measures of bias based on ARaB for the three models and across two datasets.

#### Table 5: Comparative Analysis between BERT-Tiny trained on the de-biased dataset and ADVBERT Model
<table class="tg">
<thead>
  <tr>
    <th class="tg-0pky" rowspan="2">Neural Re-ranker Model</th>
    <th class="tg-0pky" rowspan="2">Query Set</th>
    <th class="tg-0pky" rowspan="2">Training Set</th>
    <th class="tg-0pky" rowspan="2">MRR<br>@10<br></th>
    <th class="tg-0pky" colspan="4">ARaB</th>
    <th class="tg-0pky" colspan="2">LIWC</th>
  </tr>
  <tr>
    <td class="tg-0pky">TF</td>
    <td class="tg-0pky">TF (%)</td>
    <td class="tg-0pky">Boolean</td>
    <td class="tg-0pky">Boolean (%)</td>
    <td class="tg-0pky">Male Female Diff</td>
    <td class="tg-0pky"> Improvement (%)</td>
  </tr>
</thead>
<tbody>
  <tr>
    <td class="tg-0pky" rowspan="6">BERT-Tiny</td>
    <td class="tg-0pky" rowspan="3"><a href="https:https://github.com/navid-rekabsaz/GenderBias_IR/blob/master/resources/queries_gender_annotated.csv" target="_top">1765 Neutral Queries</td>
    <td class="tg-0pky">Original Dataset <a href="https://github.com/balancedbias/debiasingneuralrankers/blob/main/results/trec_runs/1765_neutral_queries/bert_tiny_original_dataset.trec" target="_top"> (Run)</td>
    <td class="tg-c3ow">0.219</td>
    <td class="tg-c3ow">0.076</td>
    <td class="tg-c3ow">-</td>
    <td class="tg-c3ow">0.063</td>
    <td class="tg-c3ow">-</td>
    <td class="tg-c3ow">0.012</td>
    <td class="tg-c3ow">-</td>
  </tr>
  <tr>
    <td class="tg-0pky">De-biased Dataset <a href="https://github.com/balancedbias/debiasingneuralrankers/blob/main/results/trec_runs/1765_neutral_queries/bert_tiny_debiased_dataset_0.25.trec"> (Run)</td>
    <td class="tg-c3ow">0.199</td>
    <td class="tg-c3ow">0.047</td>
    <td class="tg-c3ow">38.15%</td>
    <td class="tg-c3ow">0.042</td>
    <td class="tg-c3ow">32.06%</td>
    <td class="tg-c3ow">0.010</td>
    <td class="tg-c3ow">10.74%</td>
  </tr>
  <tr>
    <td class="tg-0lax">ADVBERT <a href="https://github.com/balancedbias/debiasingneuralrankers/blob/main/results/trec_runs/1765_neutral_queries/ADVBERT_tiny.trec"> (Run)</td>
    <td class="tg-baqh">0.189</td>
    <td class="tg-baqh">0.064</td>
    <td class="tg-baqh">15.78%</td>
    <td class="tg-baqh">0.058</td>
    <td class="tg-baqh">7.30%</td>
    <td class="tg-baqh">0.009</td>
    <td class="tg-baqh">24.79%</td>
  </tr>
  <tr>
    <td class="tg-0pky" rowspan="3"><a href="https://github.com/CPJKU/FairnessRetrievalResults/blob/main/resources/fairnesssensitive_queries/msmarco_passage.dev.fair.tsv" target="_top">215 Social Problematic Queries</td>
    <td class="tg-0pky">Original Dataset <a href="https://github.com/balancedbias/debiasingneuralrankers/blob/main/results/trec_runs/215_neutral_queries/bert_tiny_original_dataset.trec"> (Run)</td>
    <td class="tg-c3ow">0.162</td>
    <td class="tg-c3ow">0.005</td>
    <td class="tg-c3ow">-</td>
    <td class="tg-c3ow">0.006</td>
    <td class="tg-c3ow">-</td>
    <td class="tg-c3ow">0.005</td>
    <td class="tg-c3ow">-</td>
  </tr>
  <tr>
    <td class="tg-0pky">De-biased Dataset <a href="https://github.com/balancedbias/debiasingneuralrankers/blob/main/results/trec_runs/215_neutral_queries/bert_tiny_debiased_dataset_0.25.trec"> (Run)</td>
    <td class="tg-c3ow">0.163</td>
    <td class="tg-c3ow">0.001</td>
    <td class="tg-c3ow">79.19%</td>
    <td class="tg-c3ow">0.000</td>
    <td class="tg-c3ow">97.01%</td>
    <td class="tg-c3ow">0.005</td>
    <td class="tg-c3ow">11.11%</td>
  </tr>
  <tr>
    <td class="tg-0lax">ADVBERT <a href="https://github.com/balancedbias/debiasingneuralrankers/blob/main/results/trec_runs/215_neutral_queries/ADVBERT_tiny.trec"> (Run)</td>
    <td class="tg-baqh">0.149</td>
    <td class="tg-baqh">0.009</td>
    <td class="tg-baqh">-85.98%</td>
    <td class="tg-baqh">0.007</td>
    <td class="tg-baqh">-16.67%</td>
    <td class="tg-baqh">0.005</td>
    <td class="tg-baqh">14.81%</td>
  </tr>
</tbody>
</table>

## Resources
We release the run files, BERT models fine-tuned on all the dataset, our proposed balanced query-document pairs, and the codes for bias measurement to help the community reproduce our results. Due to the file size limitations, fine-tuned models and some of the run files are uploaded [here](https://drive.google.com/file/d/1fDply69C8_csrEe-99ZtweopHbgycbMa/view?usp=sharing).
## Usage
##### In order to achieve a balanced set of query_document pairs and train models on the de-biased dataset, one should replicate the following steps:

1. In order to generate queries for all the documents in the collection, you need to use a T5 transformer model that is capable of generating queries for a given document. For this purpose, you can use the instruction provided in the github repository of [docTTTTTquery](https://github.com/castorini/docTTTTTquery).

2. Having the query-document pairs, you need to identify the gender associated with each pair. To this end, you need to use the BERT classification model that is fine-tuned for the query gender identification task. You can access the fine-tuned model and all the resources [here](https://github.com/aminbigdeli/gender-bias-in-relevance-judgements) and identify the gender of generated queries associated with each document.
3. Now, in order to find the documents that share similar level of psychological characteristics, you need to use [LIWC](http://liwc.wpengine.com/) toolkit and represent each document by a vector of its pyschological attributes.
4. Finally, having the psychological vector representation for each male and female query-document pairs in the collection, you can use [`find_similar_pairs.py`](https://github.com/balancedbias/debiasingneuralrankers/blob/main/src/find_similar_pairs.py) to find the pairs that share similar level of psychological characteristics.
5. In order to adopt BERT transformer models and use it for passage ranking task, you should clone [OpenMatch](https://github.com/thunlp/OpenMatch) repository and train BERT-base-uncased model with the following config.
```
python inference.py \
        -task ranking \
        -model bert \
        -max_input 12800000 \
        -test queries=./data/queries.dev.small.tsv,docs=./data/collection.tsv,trec=./data/run.msmarco-passage.dev.small.trec \
        -vocab bert-base-uncased \
        -pretrain bert-base-uncased \
        -checkpoint ./checkpoints/bert-base.bin \
        -res ./results/bert-base_msmarco-dev.trec \
        -max_query_len 20 \
        -max_doc_len 150 \
        -batch_size 64 \
	-metric mrr_cut_10
```
##### In order to evaluate the performance of the models and calculate the level of gender biases inside the retirieved documents of each run file:
1. You can use the following command inside the [anserini](https://github.com/castorini/anserini) directory to evaluate the performance of run files ranked by the BERT-base-uncased models trained on different datasets:
```
tools/eval/trec_eval.9.0.4/trec_eval -c -mrecall.1000 -mmap \
 path_to_qrels_file.trec path_to_run_file.trec
```
2. You can also measure the level of psychological characteristics among the top 10 documents of female and male queries using [measure_psycho_attributes.py`](https://github.com/balancedbias/debiasingneuralrankers/blob/main/src/LIWC/measure_psycho_attributes.py):
```
python `measure_psycho_attributes.py -run path_to_run_file.trec -res path_to_results_dir.csv
```
3. In order to measure gender biases within the top 10 documents of neutral queries you can use [`runs_calculate_bias.py`](https://github.com/balancedbias/debiasingneuralrankers/blob/main/src/ARaB/runs_calculate_bias.py) and [`model_calculate_bias.py`](https://github.com/balancedbias/debiasingneuralrankers/blob/main/src/ARaB/model_calculate_bias.py) scripts for calculating the TF ARab and TF Boolean metrics introduced in Do Neural Ranking Models Intensify Gender Bias? . In addition, to measure the male affiliation and female affiliatition within the top 10 documents of neutral queries using LIWC toolkit, you can use [`measure_male_female_affiliation.py`](https://github.com/balancedbias/debiasingneuralrankers/blob/main/src/LIWC/measure_male_female_affiliation.py).
