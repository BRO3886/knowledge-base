<html>
	<head>
		<meta
			content="text/html; charset=UTF-8"
			http-equiv="content-type"
		/>
	</head>
	<body class="c27">
		<p class="c11"><span class="c5">ML Notes: CAT 2</span></p>
		<p class="c11 c8"><span class="c5"></span></p>
		<p class="c3">
			<span class="c13">Data:</span
			><span class="c2"
				>&nbsp;A set of data records (also called examples, instances
				or cases) described by
			</span>
		</p>
		<ul class="c9 lst-kix_3p9h98ototk5-0 start">
			<li class="c0 li-bullet-0">
				<span class="c10">k attributes: </span
				><span class="c2">A1, A2, &hellip; Ak. &nbsp;</span>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c10">a class: </span
				><span class="c2"
					>Each example is labelled with a pre-defined class.
				</span>
			</li>
		</ul>
		<p class="c3">
			<span class="c13">Goal:</span
			><span class="c2"
				>&nbsp;To learn a classification model from the data that can
				be used to predict the classes of new (future, or test)
				cases/instances.</span
			>
		</p>
		<p class="c3 c8"><span class="c5"></span></p>
		<p class="c3">
			<span class="c12">Supervised vs Unsupervised Learning</span>
		</p>
		<p class="c3">
			<span class="c13">Supervised learning: </span
			><span class="c20">classification </span
			><span class="c2"
				>is seen as supervised learning from examples.
			</span>
		</p>
		<ul class="c9 lst-kix_zanm8c1imzcr-0 start">
			<li class="c0 li-bullet-0">
				<span class="c2"
					>Supervision: The data (observations, measurements, etc.)
					are labeled with predefined classes. It is like that a
					&ldquo;teacher&rdquo; gives the classes (supervision).
					&nbsp;</span
				>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c2"
					>Test data are classified into these classes too.
				</span>
			</li>
		</ul>
		<p class="c3">
			<span class="c13">Unsupervised learning: </span
			><span class="c19">clustering</span>
		</p>
		<ul class="c9 lst-kix_3h492yam9vfd-0 start">
			<li class="c0 li-bullet-0">
				<span class="c2">Class labels of the data are unknown</span>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c2"
					>Given a set of data, the task is to establish the existence
					of classes or clusters in the data</span
				>
			</li>
		</ul>
		<p class="c3 c8"><span class="c2"></span></p>
		<p class="c3">
			<span class="c12">Supervised learning process: two steps</span>
		</p>
		<ol class="c9 lst-kix_69jqfbbojq1l-0 start" start="1">
			<li class="c0 li-bullet-0">
				<span class="c2"
					>Learning (training): Learn a model using the training
					data</span
				>
			</li>
		</ol>
		<ul class="c9 lst-kix_v5cm4gbeq60u-0 start">
			<li class="c3 c16 li-bullet-0">
				<span
					>Given a data set D, a task T, and a performance measure M,
					a computer system is said to </span
				><span class="c10">learn </span
				><span class="c2"
					>from D to perform the task T if after learning the
					system&rsquo;s performance on T improves as measured by
					M</span
				>
			</li>
			<li class="c3 c16 li-bullet-0">
				<span>In other words, the </span
				><span class="c10">learned model </span
				><span>helps the system to </span
				><span class="c20">perform T better </span
				><span class="c2">as compared to no learning. </span>
			</li>
		</ul>
		<ol class="c9 lst-kix_69jqfbbojq1l-0" start="2">
			<li class="c0 li-bullet-0">
				<span class="c2"
					>Testing: Test the model using unseen test data to assess
					the model accuracy</span
				>
			</li>
		</ol>
		<p class="c3 c22">
			<span
				style="
					overflow: hidden;
					display: inline-block;
					margin: 0px 0px;
					border: 0px solid #000000;
					transform: rotate(0rad) translateZ(0px);
					-webkit-transform: rotate(0rad) translateZ(0px);
					width: 297.5px;
					height: 44.2px;
				"
				><img
					alt=""
					src="images/image9.png"
					style="
						width: 297.5px;
						height: 44.2px;
						margin-left: 0px;
						margin-top: 0px;
						transform: rotate(0rad) translateZ(0px);
						-webkit-transform: rotate(0rad) translateZ(0px);
					"
					title="" /></span
			><span
				style="
					overflow: hidden;
					display: inline-block;
					margin: 0px 0px;
					border: 0px solid #000000;
					transform: rotate(0rad) translateZ(0px);
					-webkit-transform: rotate(0rad) translateZ(0px);
					width: 233.32px;
					height: 60.99px;
				"
				><img
					alt=""
					src="images/image7.png"
					style="
						width: 233.32px;
						height: 60.99px;
						margin-left: 0px;
						margin-top: 0px;
						transform: rotate(0rad) translateZ(0px);
						-webkit-transform: rotate(0rad) translateZ(0px);
					"
					title=""
			/></span>
		</p>
		<p class="c3 c8"><span class="c2"></span></p>
		<p class="c3">
			<span class="c12">Fundamental Assumption of Learning</span>
		</p>
		<p class="c3">
			<span class="c2"
				>The distribution of training examples is identical to the
				distribution of test examples (including future unseen
				examples).
			</span>
		</p>
		<ul class="c9 lst-kix_5e2dulrpasdu-0 start">
			<li class="c0 li-bullet-0">
				<span class="c2"
					>In practice, this assumption is often violated to a certain
					degree.
				</span>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c2"
					>Strong violations will clearly result in poor
					classification accuracy.
				</span>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c2"
					>To achieve good accuracy on the test data, training
					examples must be sufficiently representative of the test
					data.
				</span>
			</li>
		</ul>
		<p class="c3 c8"><span class="c5"></span></p>
		<p class="c3"><span class="c12">Decision Tree</span></p>
		<p class="c3 c8"><span class="c12"></span></p>
		<p class="c3"><span class="c5">Algorithms</span></p>
		<p class="c3 c8"><span class="c2"></span></p>
		<a id="t.86d77b78d54b4e0fdcfa9f27cf735956f3d8e455"></a
		><a id="t.0"></a>
		<table class="c21">
			<tbody>
				<tr class="c7">
					<td class="c23" colspan="1" rowspan="1">
						<p class="c3">
							<span class="c6">Greedy: Divide and Conquer</span>
						</p>
						<ul class="c9 lst-kix_gapx7fw5v83h-0 start">
							<li class="c0 li-bullet-0">
								<span class="c2"
									>Assume attributes are categorical now (continuous
									attributes can be handled too)</span
								>
							</li>
							<li class="c0 li-bullet-0">
								<span class="c2"
									>Tree is constructed in a top-down recursive
									manner</span
								>
							</li>
							<li class="c0 li-bullet-0">
								<span class="c2"
									>At start, all the training examples are at the
									root</span
								>
							</li>
							<li class="c0 li-bullet-0">
								<span class="c2"
									>Examples are partitioned recursively based on
									selected attributes</span
								>
							</li>
							<li class="c0 li-bullet-0">
								<span class="c2"
									>Attributes are selected on the basis of an impurity
									function (e.g., information gain)</span
								>
							</li>
						</ul>
						<p class="c3">
							<span class="c19"
								>Conditions for stopping Partitioning</span
							>
						</p>
						<ul class="c9 lst-kix_9nkukcdi3cby-0 start">
							<li class="c0 li-bullet-0">
								<span class="c2"
									>All examples for a given node belong to the same
									class</span
								>
							</li>
							<li class="c0 li-bullet-0">
								<span class="c2"
									>There are no remaining attributes for further
									partitioning &ndash; majority class is the
									leaf</span
								>
							</li>
							<li class="c0 li-bullet-0">
								<span class="c2">There are no examples left</span>
							</li>
						</ul>
						<p class="c15 c8"><span class="c2"></span></p>
					</td>
				</tr>
			</tbody>
		</table>
		<p class="c3 c8"><span class="c2"></span></p>
		<p class="c11">
			<span
				style="
					overflow: hidden;
					display: inline-block;
					margin: 0px -0px;
					border: 1.33px solid #000000;
					transform: rotate(0rad) translateZ(0px);
					-webkit-transform: rotate(0rad) translateZ(0px);
					width: 520.42px;
					height: 421.13px;
				"
				><img
					alt=""
					src="images/image11.png"
					style="
						width: 520.42px;
						height: 421.13px;
						margin-left: 0px;
						margin-top: 0px;
						transform: rotate(0rad) translateZ(0px);
						-webkit-transform: rotate(0rad) translateZ(0px);
					"
					title=""
			/></span>
		</p>
		<p class="c3 c8"><span class="c2"></span></p>
		<p class="c3">
			<span class="c5"
				>How to choose a root to partition data in a decision
				tree?</span
			>
		</p>
		<ul class="c9 lst-kix_hy69ojzb320r-0 start">
			<li class="c0 li-bullet-0">
				<span class="c2"
					>The key to building a decision tree - which attribute to
					choose in order to branch.
				</span>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c2"
					>The objective is to reduce impurity or uncertainty in data
					as much as possible.</span
				>
			</li>
		</ul>
		<ul class="c9 lst-kix_hy69ojzb320r-1 start">
			<li class="c3 c4 li-bullet-0">
				<span class="c2"
					>A subset of data is pure if all instances belong to the
					same class.
				</span>
			</li>
		</ul>
		<ul class="c9 lst-kix_hy69ojzb320r-0">
			<li class="c0 li-bullet-0">
				<span
					>The heuristic in C4.5 is to choose the attribute with the
					maximum Information Gain or Gain Ratio based on </span
				><span class="c5">information theory.</span>
			</li>
		</ul>
		<p class="c3 c8"><span class="c2"></span></p>
		<p class="c3">
			<span class="c13">Information Theory: </span
			><span class="c2"
				>provides a mathematical basis for measuring the information
				content</span
			>
		</p>
		<p class="c3 c8"><span class="c5"></span></p>
		<p class="c3">
			<span class="c13">Entropy: </span
			><span class="c2"
				>We use entropy as a measure of impurity or disorder of data
				set D. (Or, a measure of information in a tree)</span
			>
		</p>
		<p class="c3 c8"><span class="c2"></span></p>
		<p class="c3">
			<span class="c5">Issues in Decision Tree Learning</span>
		</p>
		<ol class="c9 lst-kix_lbd0q5hrfye0-0 start" start="1">
			<li class="c0 li-bullet-0">
				<span>Avoid overfitting in classification<br /></span
				><span class="c10">Overfitting</span
				><span class="c2"
					>: &nbsp;A tree may overfit the training data
				</span>
			</li>
		</ol>
		<ul class="c9 lst-kix_lbd0q5hrfye0-1 start">
			<li class="c3 c4 li-bullet-0">
				<span class="c2"
					>Good accuracy on training data but poor on test data</span
				>
			</li>
			<li class="c3 c4 li-bullet-0">
				<span class="c2"
					>Symptoms: tree too deep and too many branches, some may
					reflect anomalies due to noise or outliers</span
				>
			</li>
		</ul>
		<p class="c3 c17">
			<span class="c6">How to avoid overfitting?</span>
		</p>
		<p class="c3 c17">
			<span class="c2"
				>Two approaches to avoid overfitting: pre-pruning and
				post-pruning</span
			>
		</p>
		<ol class="c9 lst-kix_f1u9odc868e6-0 start" start="1">
			<li class="c3 c4 li-bullet-0">
				<span class="c13">Pre-pruning</span
				><span class="c2">: Halt tree construction early</span>
			</li>
		</ol>
		<ul class="c9 lst-kix_5tgsma6dk7af-0 start">
			<li class="c1 li-bullet-0">
				<span class="c2"
					>Difficult to decide because we do not know what may happen
					subsequently if we keep growing the tree.
				</span>
			</li>
		</ul>
		<ol class="c9 lst-kix_f1u9odc868e6-0" start="2">
			<li class="c3 c4 li-bullet-0">
				<span class="c13">Post-pruning</span
				><span class="c2"
					>: Remove branches or sub-trees from a &ldquo;fully
					grown&rdquo; tree.</span
				>
			</li>
		</ol>
		<ul class="c9 lst-kix_pgk9kyyrpe1-0 start">
			<li class="c1 li-bullet-0">
				<span class="c2"
					>This method is commonly used. C4.5 uses a statistical
					method to estimate the errors at each node for pruning.
				</span>
			</li>
			<li class="c1 li-bullet-0">
				<span class="c2"
					>A validation set may be used for pruning as well.</span
				>
			</li>
		</ul>
		<ol class="c9 lst-kix_lbd0q5hrfye0-0" start="2">
			<li class="c0 li-bullet-0">
				<span class="c2">From tree to rules, and rule pruning</span>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c2">Handling of miss values</span>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c2">Handing skewed distributions</span>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c2"
					>Handling attributes and classes with different costs.
				</span>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c2">Attribute construction</span>
			</li>
		</ol>
		<p class="c3 c8"><span class="c5"></span></p>
		<p class="c3">
			<span class="c20 c13">Evaluating classification methods</span>
		</p>
		<p class="c3"><span class="c5">Terms</span></p>
		<ul class="c9 lst-kix_w0pdl0fe16gj-0 start">
			<li class="c0 li-bullet-0">
				<span class="c2">Predictive accuracy</span>
			</li>
		</ul>
		<p class="c3 c22"><img src="images/image1.png" /></p>
		<ul class="c9 lst-kix_plpptt1l1ldx-0 start">
			<li class="c0 li-bullet-0">
				<span class="c2">Efficiency</span>
			</li>
		</ul>
		<ul class="c9 lst-kix_plpptt1l1ldx-1 start">
			<li class="c1 li-bullet-0">
				<span class="c2">time to construct the model</span>
			</li>
			<li class="c1 li-bullet-0">
				<span class="c2">time to use the model</span>
			</li>
		</ul>
		<ul class="c9 lst-kix_plpptt1l1ldx-0">
			<li class="c0 li-bullet-0">
				<span class="c2"
					>Robustness: handling noise and missing values</span
				>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c2"
					>Scalability: efficiency in disk-resident databases
				</span>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c2"
					>Interpretability: understandable insight provided by the
					model</span
				>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c2"
					>Compactness of the model: size of the tree, or the number
					of rules.
				</span>
			</li>
		</ul>
		<p class="c3 c8"><span class="c2"></span></p>
		<p class="c3"><span class="c5">Evaluation Methods</span></p>
		<ul class="c9 lst-kix_djgmjujhpanv-0 start">
			<li class="c0 li-bullet-0">
				<span class="c13">Holdout set:</span
				><span
					>&nbsp;The available data set D is divided into two disjoint
					subsets, the training set </span
				><span>D</span><span class="c24">train</span
				><span>&nbsp;(for learning a model) the test set D</span
				><span class="c24">test</span
				><span class="c2">&nbsp;(for testing the model).</span>
			</li>
		</ul>
		<ul class="c9 lst-kix_djgmjujhpanv-1 start">
			<li class="c3 c4 li-bullet-0">
				<span class="c2"
					>Important: training set should not be used in testing and
					the test set should not be used in learning since an unseen
					test set provides an unbiased estimate of accuracy.
				</span>
			</li>
			<li class="c3 c4 li-bullet-0">
				<span class="c2"
					>The test set is also called the holdout set. (the examples
					in the original data set D are all labeled with classes.)
				</span>
			</li>
			<li class="c3 c4 li-bullet-0">
				<span class="c2"
					>This method is mainly used when the data set D is large.
				</span>
			</li>
		</ul>
		<ul class="c9 lst-kix_djgmjujhpanv-0">
			<li class="c0 li-bullet-0">
				<span class="c13">n-fold cross-validation: </span
				><span class="c2"
					>The available data is partitioned into n equal-size
					disjoint subsets.
				</span>
			</li>
		</ul>
		<ul class="c9 lst-kix_djgmjujhpanv-1 start">
			<li class="c3 c4 li-bullet-0">
				<span class="c2"
					>Use each subset as the test set and combine the rest n-1
					subsets as the training set to learn a classifier</span
				>
			</li>
			<li class="c3 c4 li-bullet-0">
				<span class="c2"
					>The procedure is run n times, which give n accuracies.
				</span>
			</li>
			<li class="c3 c4 li-bullet-0">
				<span class="c2"
					>The final estimated accuracy of learning is the average of
					the n accuracies.
				</span>
			</li>
			<li class="c3 c4 li-bullet-0">
				<span class="c2"
					>10-fold and 5-fold cross-validations are commonly used.
					&nbsp;</span
				>
			</li>
			<li class="c3 c4 li-bullet-0">
				<span
					>This method is used when the available data is not large.
				</span>
			</li>
		</ul>
		<ul class="c9 lst-kix_djgmjujhpanv-0">
			<li class="c0 li-bullet-0">
				<span class="c13">Leave-one-out cross-validation: </span
				><span class="c2"
					>This method is used when the data set is very small.
				</span>
			</li>
		</ul>
		<ul class="c9 lst-kix_djgmjujhpanv-1 start">
			<li class="c3 c4 li-bullet-0">
				<span class="c2"
					>It is a special case of cross-validation</span
				>
			</li>
			<li class="c3 c4 li-bullet-0">
				<span class="c2"
					>Each fold of the cross validation has only a single test
					example and all the rest of the data is used in training.
				</span>
			</li>
			<li class="c3 c4 li-bullet-0">
				<span class="c2"
					>If the original data has m examples, this is m-fold
					cross-validation
				</span>
			</li>
		</ul>
		<ul class="c9 lst-kix_djgmjujhpanv-0">
			<li class="c0 li-bullet-0">
				<span class="c13">Validation set: </span
				><span class="c2"
					>the available data is divided into three subsets, a
					training set, a validation set and a test set.
				</span>
			</li>
		</ul>
		<ul class="c9 lst-kix_djgmjujhpanv-1 start">
			<li class="c3 c4 li-bullet-0">
				<span class="c2"
					>A validation set is used frequently for estimating
					parameters in learning algorithms.
				</span>
			</li>
			<li class="c3 c4 li-bullet-0">
				<span class="c2"
					>In such cases, the values that give the best accuracy on
					the validation set are used as the final parameter values.
				</span>
			</li>
			<li class="c3 c4 li-bullet-0">
				<span class="c2"
					>Cross-validation can be used for parameter estimating as
					well.
				</span>
			</li>
		</ul>
		<p class="c3 c8"><span class="c2"></span></p>
		<p class="c3"><span class="c12">Classification measures</span></p>
		<ul class="c9 lst-kix_ufdg6u79jg9c-0 start">
			<li class="c3 c16 li-bullet-0">
				<span class="c2"
					>In classification involving skewed or highly imbalanced
					data, e.g., network intrusion and financial fraud
					detections, we are interested only in the minority class.
				</span>
			</li>
		</ul>
		<ul class="c9 lst-kix_ufdg6u79jg9c-1 start">
			<li class="c1 li-bullet-0">
				<span class="c2"
					>High accuracy does not mean any intrusion is detected.
				</span>
			</li>
			<li class="c1 li-bullet-0">
				<span class="c2"
					>E.g., 1% intrusion. Achieve 99% accuracy by doing nothing.
				</span>
			</li>
		</ul>
		<ul class="c9 lst-kix_ufdg6u79jg9c-0">
			<li class="c3 c16 li-bullet-0">
				<span class="c2"
					>The class of interest is commonly called the positive
					class, and the rest negative classes.</span
				>
			</li>
		</ul>
		<p class="c3">
			<span class="c5">Precision and Recall measures</span>
		</p>
		<p class="c11">
			<span
				style="
					overflow: hidden;
					display: inline-block;
					margin: 0px 0px;
					border: 0px solid #000000;
					transform: rotate(0rad) translateZ(0px);
					-webkit-transform: rotate(0rad) translateZ(0px);
					width: 419.5px;
					height: 211.77px;
				"
				><img
					alt=""
					src="images/image8.png"
					style="
						width: 419.5px;
						height: 211.77px;
						margin-left: 0px;
						margin-top: 0px;
						transform: rotate(0rad) translateZ(0px);
						-webkit-transform: rotate(0rad) translateZ(0px);
					"
					title=""
			/></span>
		</p>
		<p class="c11">
			<span
				style="
					overflow: hidden;
					display: inline-block;
					margin: 0px 0px;
					border: 0px solid #000000;
					transform: rotate(0rad) translateZ(0px);
					-webkit-transform: rotate(0rad) translateZ(0px);
					width: 279.5px;
					height: 56.71px;
				"
				><img
					alt=""
					src="images/image12.png"
					style="
						width: 279.5px;
						height: 56.71px;
						margin-left: 0px;
						margin-top: 0px;
						transform: rotate(0rad) translateZ(0px);
						-webkit-transform: rotate(0rad) translateZ(0px);
					"
					title=""
			/></span>
		</p>
		<p class="c3 c8"><span class="c5"></span></p>
		<ol class="c9 lst-kix_n241nr3b65kb-0 start" start="1">
			<li class="c0 li-bullet-0">
				<span class="c13">Precision p</span
				><span class="c2"
					>&nbsp;is the number of correctly classified positive
					examples divided by the total number of examples that are
					classified as positive.
				</span>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c13">Recall r</span
				><span class="c2"
					>&nbsp;is the number of correctly classified positive
					examples divided by the total number of actual positive
					examples in the test set.
				</span>
			</li>
		</ol>
		<p class="c3 c8"><span class="c19"></span></p>
		<p class="c3">
			<span class="c13">F1-value (also called F1-score): </span
			><span>harmonic mean of p and r </span
			><img src="images/image2.png" /><span class="c14">)</span>
		</p>
		<ul class="c9 lst-kix_3ap67mc1e5mx-0 start">
			<li class="c0 li-bullet-0">
				<span class="c2"
					>The harmonic mean of two numbers tends to be closer to the
					smaller of the two.
				</span>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c2"
					>For F1-value to be large, both p and r must be large.
				</span>
			</li>
		</ul>
		<p class="c3 c8"><span class="c14 c26"></span></p>
		<p class="c3">
			<span class="c13"
				>ROC (Receive operating characteristics ) Curve: </span
			><span class="c2"
				>It is a plot of the true positive rate (TPR) against the
				false positive rate (FPR).</span
			>
		</p>
		<p class="c3">
			<span>True Positive Rate: </span
			><img src="images/image3.png" /><span class="c14">&nbsp;</span
			><span>False Positive Rate: </span
			><img src="images/image4.png" />
		</p>
		<p class="c3 c8"><span class="c14 c13 c29"></span></p>
		<p class="c3">
			<span class="c5">Sensitivity and Specificity: </span>
		</p>
		<ul class="c9 lst-kix_zguewh3b03zr-0 start">
			<li class="c0 li-bullet-0">
				<span class="c2">Sensitivity: Same as TPR</span>
			</li>
			<li class="c0 li-bullet-0">
				<span>Specificity: Also called True Negative Rate: </span
				><img src="images/image5.png" />
			</li>
			<li class="c0 li-bullet-0">
				<span class="c2">FPR = 1 - specificity</span>
			</li>
		</ul>
		<p class="c3 c8"><span class="c2"></span></p>
		<p class="c3">
			<span class="c12">Naive Bayes Classification</span>
		</p>
		<p class="c3">
			<span
				>A machine learning algorithm - classification technique. </span
			><span class="c6"
				>Naive Bayes is used when the output variable is discrete.
			</span>
		</p>
		<ul class="c9 lst-kix_tfj6dtlc5p0g-0 start">
			<li class="c0 li-bullet-0">
				<span class="c13">Conditional probability</span
				><span class="c2"
					>: a measure of the probability of event A occurring given
					that another event has occurred. For example, &ldquo;what is
					the probability that it will rain given that it is
					cloudy?&rdquo; is an example of conditional
					probability.</span
				>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c13">Joint Probability</span
				><span class="c2"
					>: a measure that calculates the likelihood of two or more
					events occurring at the same time.</span
				>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c13">Proportionality</span
				><span class="c2"
					>: refers to the relationship between two quantities that
					are multiplicatively connected to a constant, or in simpler
					terms, whether their ratio yields a constant.</span
				>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c13">Bayes Theorem</span
				><span class="c2"
					>: according to Wikipedia, Bayes&rsquo; Theorem describes
					the probability of an event (posterior) based on the prior
					knowledge of conditions that might be related to the
					event.</span
				>
			</li>
		</ul>
		<p class="c3 c8"><span class="c2"></span></p>
		<a id="t.eea1f2efd189d2e4f15b07d4116b9568e355b727"></a
		><a id="t.1"></a>
		<table class="c21">
			<tbody>
				<tr class="c7">
					<td class="c23" colspan="1" rowspan="1">
						<p class="c3">
							<span class="c5">Steps (Algorithm):</span>
						</p>
						<ol class="c9 lst-kix_k9us6aws6d5m-0 start" start="1">
							<li class="c3 c16 li-bullet-0">
								<span class="c6">Step 1: &nbsp;Frequency Table</span>
							</li>
						</ol>
						<p class="c3 c22">
							<span class="c2"
								>First, we need to convert the data into a frequency
								table, so that we can get the values of P(X|y) and
								P(X). Recall that we are solving for P(y|X):</span
							>
						</p>
						<ol class="c9 lst-kix_k9us6aws6d5m-0" start="2">
							<li class="c3 c16 li-bullet-0">
								<span class="c6"
									>Step 2: Frequencies into ratios or conditional
									probabilities
								</span>
							</li>
						</ol>
						<p class="c3 c22">
							<span class="c2"
								>we want to convert the frequencies into ratios or
								conditional probabilities:</span
							>
						</p>
						<ol class="c9 lst-kix_k9us6aws6d5m-0" start="3">
							<li class="c3 c16 li-bullet-0">
								<span class="c6"
									>Step 3: Proportionality equation to predict y,
									given X</span
								>
							</li>
						</ol>
						<p class="c3 c22">
							<span class="c2"
								>Finally, we can use the proportionality equation to
								predict y, given X.</span
							>
						</p>
					</td>
				</tr>
			</tbody>
		</table>
		<p class="c3 c8"><span class="c2"></span></p>
		<p class="c3">
			<span class="c5">Naive Bayes&rsquo; Applications</span>
		</p>
		<ul class="c9 lst-kix_n9y92x7wayic-0 start">
			<li class="c0 li-bullet-0">
				<span class="c13">Real-time prediction:</span
				><span class="c2"
					>&nbsp;Because Naive Bayes is fast and it&rsquo;s based on
					Bayesian statistics, it works well at making predictions in
					real-time. In fact, a lot of popular real-time models or
					online models are based on Bayesian statistics.</span
				>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c13">Multiclass prediction:</span
				><span class="c2"
					>&nbsp;As previously stated, Naive Bayes works well when
					there are more than two classes for the output
					variable.</span
				>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c13">Text classification:</span
				><span class="c2"
					>&nbsp;Text classification also includes sub-applications
					like spam filtering and sentiment analysis. Since Naive
					Bayes works best with discrete variables, it tends to work
					well in these applications.</span
				>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c13">Recommendation systems:</span
				><span class="c2"
					>&nbsp;Naive Bayes is commonly used alongside other
					algorithms like Collaborative Filtering to build
					recommendations systems like Netflix&rsquo;s recommended for
					you section, or Amazon&rsquo;s recommended products, or
					Spotify&rsquo;s recommended songs.</span
				>
			</li>
		</ul>
		<p class="c3 c8"><span class="c2"></span></p>
		<p class="c3"><span class="c5">Issues with Naive Bayes</span></p>
		<ul class="c9 lst-kix_qdtk9h1qk5nf-0 start">
			<li class="c0 li-bullet-0">
				<span class="c13">Numeric attributes:</span
				><span class="c2"
					>&nbsp;Na&iuml;ve Bayesian learning assumes that all
					attributes are categorical. Numeric attributes need to be
					discretized.</span
				>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c13">Zero counts</span
				><span class="c2"
					>: An particular attribute value never occurs together with
					a class in the training set. We need smoothing.</span
				>
			</li>
		</ul>
		<p class="c3 c22">
			<span
				style="
					overflow: hidden;
					display: inline-block;
					margin: 0px 0px;
					border: 0px solid #000000;
					transform: rotate(0rad) translateZ(0px);
					-webkit-transform: rotate(0rad) translateZ(0px);
					width: 160.5px;
					height: 40.13px;
				"
				><img
					alt=""
					src="images/image10.png"
					style="
						width: 160.5px;
						height: 40.13px;
						margin-left: 0px;
						margin-top: 0px;
						transform: rotate(0rad) translateZ(0px);
						-webkit-transform: rotate(0rad) translateZ(0px);
					"
					title=""
			/></span>
		</p>
		<ul class="c9 lst-kix_qdtk9h1qk5nf-0">
			<li class="c0 li-bullet-0">
				<span class="c13">Missing values:</span
				><span class="c2">&nbsp;Missing values are Ignored </span>
			</li>
		</ul>
		<p class="c3 c8"><span class="c5"></span></p>
		<p class="c3">
			<span class="c5"
				>Advantages and Disadvantages of Naive Bayes</span
			>
		</p>
		<a id="t.23026b7eafcbddfe7831d42deb7836ce9ee43cf3"></a
		><a id="t.2"></a>
		<table class="c21">
			<tbody>
				<tr class="c7">
					<td class="c18" colspan="1" rowspan="1">
						<p class="c15"><span class="c5">Advantages</span></p>
					</td>
					<td class="c18" colspan="1" rowspan="1">
						<p class="c15"><span class="c5">Disadvantages</span></p>
					</td>
				</tr>
				<tr class="c7">
					<td class="c18" colspan="1" rowspan="1">
						<p class="c15">
							<span class="c2">Easy to implement</span>
						</p>
						<p class="c15"><span class="c2">Very efficient</span></p>
						<p class="c15">
							<span>Good results obtained in many applications</span>
						</p>
					</td>
					<td class="c18" colspan="1" rowspan="1">
						<p class="c15">
							<span
								>Assumption: class conditional independence, therefore
								loss of accuracy when the assumption is seriously
								violated (those highly correlated data sets)</span
							>
						</p>
					</td>
				</tr>
			</tbody>
		</table>
		<p class="c3 c8"><span class="c5"></span></p>
		<p class="c3"><span class="c12">Support Vector Machines</span></p>
		<p class="c3">
			<span>SVMs are </span
			><span class="c20">linear classifiers </span
			><span
				>that find a hyperplane to separate two classes of data, </span
			><span class="c6">positive and negative. </span>
		</p>
		<ul class="c9 lst-kix_1lvienj2z6zc-0 start">
			<li class="c0 li-bullet-0">
				<span class="c10">Kernel functions </span
				><span>are used for nonlinear separation.</span>
			</li>
		</ul>
		<ul class="c9 lst-kix_k07lwf6jlrbb-0 start">
			<li class="c0 li-bullet-0">
				<span class="c2"
					>SVM not only has a rigorous theoretical foundation, but
					also performs classification more accurately than most other
					methods in applications, especially for high dimensional
					data.</span
				>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c2"
					>It is perhaps the best classifier for text classification.
				</span>
			</li>
		</ul>
		<p class="c3 c8"><span class="c2"></span></p>
		<p class="c3"><span class="c5">Issues with SVM</span></p>
		<ul class="c9 lst-kix_io56kld7ootj-0 start">
			<li class="c0 li-bullet-0">
				<span class="c2"
					>SVM works only in a real-valued space. For a categorical
					attribute, we need to convert its categorical values to
					numeric values.
				</span>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c2"
					>SVM does only two-class classification. For multi-class
					problems, some strategies can be applied, e.g.,
					one-against-rest, and error-correcting output coding.
				</span>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c2"
					>The hyperplane produced by SVM is hard to understand by
					human users. The matter is made worse by kernels. Thus, SVM
					is commonly used in applications that do not require human
					understanding.</span
				>
			</li>
		</ul>
		<p class="c3 c8"><span class="c2"></span></p>
		<p class="c3">
			<span class="c12">KNN: K nearest Neighbours</span>
		</p>
		<p class="c3">
			<span
				>One of the simplest supervised learning algorithms. It
				classifies a data point based on how it&rsquo;s </span
			><span class="c10">k</span
			><span class="c2"
				>&nbsp;closest neighbours are classified.</span
			>
		</p>
		<p class="c3 c8"><span class="c2"></span></p>
		<ul class="c9 lst-kix_u4piyhhcjedv-0 start">
			<li class="c0 li-bullet-0">
				<span class="c2"
					>k is usually chosen empirically via a validation set or
					cross-validation by trying a range of k values.
				</span>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c2"
					>Distance function is crucial, but depends on applications.
				</span>
			</li>
		</ul>
		<p class="c3 c8"><span class="c2"></span></p>
		<a id="t.bd89d5df546ea2da83a719dbbe473782b59d537d"></a
		><a id="t.3"></a>
		<table class="c21">
			<tbody>
				<tr class="c7">
					<td class="c23" colspan="1" rowspan="1">
						<p class="c3">
							<span class="c5">Algorithm KNN(D,d,k)</span>
						</p>
						<ol class="c9 lst-kix_ybbok8g7zzad-0 start" start="1">
							<li class="c0 li-bullet-0">
								<span>Compute the distance between </span
								><span class="c10">d </span
								><span class="c2">and every example in D</span>
							</li>
							<li class="c0 li-bullet-0">
								<span>Choose the </span><span class="c10">k </span
								><span>examples in </span><span class="c10">D</span
								><span>&nbsp;that are nearest to </span
								><span class="c10">d</span
								><span>, denote the set by P ( </span
								><img src="images/image6.png" /><span class="c2"
									>&nbsp;D)</span
								>
							</li>
							<li class="c0 li-bullet-0">
								<span>Assign </span><span class="c10">d </span
								><span
									>the class that is the most frequent class in </span
								><span class="c10">P</span
								><span class="c2">&nbsp;(or the majority class)</span>
							</li>
						</ol>
					</td>
				</tr>
			</tbody>
		</table>
		<p class="c3 c8"><span class="c2"></span></p>
		<p class="c3"><span class="c5">Pros and Cons of KNN</span></p>
		<a id="t.d0efee9ebeb0da02ba77ccad64b6bd24985cbeff"></a
		><a id="t.4"></a>
		<table class="c21">
			<tbody>
				<tr class="c7">
					<td class="c18" colspan="1" rowspan="1">
						<p class="c15"><span class="c5">Pros</span></p>
					</td>
					<td class="c18" colspan="1" rowspan="1">
						<p class="c15"><span class="c5">Cons</span></p>
					</td>
				</tr>
				<tr class="c7">
					<td class="c18" colspan="1" rowspan="1">
						<ul class="c9 lst-kix_1468kxek2pqa-0 start">
							<li class="c0 li-bullet-0">
								<span class="c2">Simple to implement</span>
							</li>
							<li class="c0 li-bullet-0">
								<span class="c2"
									>Flexible to feature/distance choices</span
								>
							</li>
							<li class="c0 li-bullet-0">
								<span class="c2"
									>Naturally handles multi-class cases</span
								>
							</li>
							<li class="c0 li-bullet-0">
								<span class="c2"
									>Can do well in practice with enough representative
									data</span
								>
							</li>
						</ul>
					</td>
					<td class="c18" colspan="1" rowspan="1">
						<ul class="c9 lst-kix_uaemtug07a9u-0 start">
							<li class="c15 c25 c17 li-bullet-0">
								<span class="c2"
									>Need to determine the value of parameter K (number
									of nearest neighbors)</span
								>
							</li>
							<li class="c15 c25 c17 li-bullet-0">
								<span class="c2"
									>Computation cost is quite high because we need to
									compute the distance of each query instance to all
									training samples.</span
								>
							</li>
							<li class="c15 c17 c25 li-bullet-0">
								<span class="c2">Storage of data</span>
							</li>
							<li class="c15 c25 c17 li-bullet-0">
								<span class="c2"
									>Must know we have a meaningful distance
									function.</span
								>
							</li>
						</ul>
					</td>
				</tr>
			</tbody>
		</table>
		<p class="c3 c8"><span class="c2"></span></p>
		<p class="c3"><span class="c5">Discussions</span></p>
		<ul class="c9 lst-kix_r5zlqspxnx33-0 start">
			<li class="c0 li-bullet-0">
				<span class="c2"
					>kNN can deal with complex and arbitrary decision
					boundaries.</span
				>
			</li>
			<li class="c0 li-bullet-0">
				<span
					>Despite its simplicity, researchers have shown that the
					classification accuracy of kNN can be quite strong and in
					many cases as accurate as those elaborated methods.</span
				>
			</li>
		</ul>
		<ul class="c9 lst-kix_3ll8rugcg6xb-0 start">
			<li class="c0 li-bullet-0">
				<span class="c2">kNN is slow at the classification time</span>
			</li>
			<li class="c0 li-bullet-0">
				<span class="c2"
					>kNN does not produce an understandable model
				</span>
			</li>
		</ul>
		<p class="c3 c8"><span class="c2"></span></p>
		<p class="c3 c8"><span class="c2"></span></p>
	</body>
</html>
