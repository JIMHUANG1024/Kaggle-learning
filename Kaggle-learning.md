# Machine Learning Explainability
# Permutation Importance

可以将data的某一column进行打乱，然后测试其对准确性的影响，从而选择data的有效特征，主要应用的模块为eli5 PermutationImportance

# Partial Plots

实际上也是判断数据对于结果的影响，数据波动越大越长则认为对结果影响越大，2D图基本算是一个相关图，两个变量的相关性....官方解释这些旨在解决我在听人们讨论部分依赖图时听到的一些常见误解。例如，我听说有人说，如果局部绘图是平坦的，则变量一定无关紧要……否则您可以放心地将其删除。但是您已经证明，即使创建平坦的局部图，创建非常重要的解决方案也是错误的。我听说有人声称波动（某些东西不是单调的）可能反映了模型中的假设。 尽管在某些情况下这可能是可行的，但通过显示原始数据的来源已证明并非如此。更普遍地说，我认为能够在这些洞察图中看到的内容与原始数据中的哪种类型的原因之间来回切换非常重要。 因此，我希望您能练习此技能，并减少我上面描述的错误类型。

# Intermediate Machine Learning
# Missing Value

主要就是解决如何应对数据缺失的办法，方法有三种：

1.直接删除

2.Imputer。填补平均值（mean）常数（constant）最多数（most_frequence）主要应用的类：from sklearn.impute import SimpleImputer

3.Onehot。基于方法2把初始缺失值的位置记录下来，也就是在各个特征值后多加一列。

# Categorical Variables

主要解决的是非数值特征的问题，方法和上面类似也有三种：

1.直接删除

2.将不同类赋值，例如红黄蓝...对应123...,主要应用的类：from sklearn.preprocessing import LabelEncoder

3.Onehot。和上述一样，原理如下图，主要应用的类： from sklearn.preprocessing import OneHotEncoder
![image](https://user-images.githubusercontent.com/77168062/117412694-a4f52480-af47-11eb-9957-058ed945e1a8.png)

# Pipelines

主要就是简化上述的两大步骤的数据处理，更像是复合一起。

from sklearn.compose import ColumnTransformer

from sklearn.pipeline import Pipeline

from sklearn.impute import SimpleImputer

from sklearn.preprocessing import OneHotEncoder

# Cross-Validation

交叉验证法，简单来说就是把数据分成n份，然后依次把一份当作验证集，去验证数据的可靠性。这适用于小数据上，大数据集上的数据够肯定是数据更可靠一点。主要应用的类：

from sklearn.model_selection import cross_val_score

