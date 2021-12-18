# Fraud Detection Using Self Organizing Maps (SOM)

Fraud detection is an example of anomaly detection, which is a broader topic in machine learning and artificial intelligence (AI), and suffers from the uncertainty in defining an anomaly (or outlier) and difficulty in outcome verification and performance monitoring. Most anomaly detection methods could be considered as unsupervised or semi-supervised learning problems, however if we have enough labeled or verified data in our database to learn from it, then supervised learning could be used to build the detection model.

Frauds in credit card transactions are common today as most of us are using the credit card payment methods more frequently. This is due to the advancement of Technology and increase in online transaction resulting in frauds causing huge financial loss. Therefore, there is need for effective methods to reduce the loss. In addition, fraudsters find ways to steal the credit card information of the user by sending fake SMS and calls, also through masquerading attack, phishing attack and so on.

### Fraud Detection [Code](https://github.com/anupam215769/Fraud-Detection-SOM-DL/blob/main/SOM.ipynb) OR <a href="https://colab.research.google.com/github/anupam215769/Fraud-Detection-SOM-DL/blob/main/SOM.ipynb"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a>

> Don't forget to add Required Data files in colab. Otherwise it won't work.


## Self Organizing Maps

A self-organizing map (SOM) is a type of artificial neural network (ANN) that is trained using unsupervised learning to produce a low-dimensional (typically two-dimensional), discretized representation of the input space of the training samples, called a map, and is therefore a method to do dimensionality reduction. Self-organizing maps differ from other artificial neural networks as they apply competitive learning as opposed to error-correction learning (such as backpropagation with gradient descent), and in the sense that they use a neighborhood function to preserve the topological properties of the input space.


**What is the core purpose of SOMs?**

The short answer would be reducing dimensionality. The example below of a SOM comes from a paper discussing an amazingly interesting application of self-organizing maps in astronomy.

![som](https://i.imgur.com/WopLWeI.png)

The example shows a complex data set consisting of a massive amount of columns and dimensions and demonstrates how that data set's dimensionality can be reduced.

So, instead of having to deal with hundreds of rows and columns (because who would want that!), the data is processed into a simplified map; that's what we call a self-organizing map. The map provides you with a two-dimensional representation of the exact same data set; one that is easier to read.

![som](https://i.imgur.com/clwiupS.png)

In this case, we got the data set from the World Bank containing all 39 indicators of human development, processed them into a SOM, and then applied that to a world map.



For instance, with artificial neural networks we multiplied the input node's value by the weight and, finally, applied an activation function. With SOMs, on the other hand, there is no activation function.

Weights are not separate from the nodes here. In an SOM, the weights belong to the output node itself. Instead of being the result of adding up the weights, the output node in an SOM contains the weights as its coordinates. Carrying these weights, it sneakily tries to find its way into the input space.

In this example, we have a 3D dataset, and each of the input nodes represents an x-coordinate. The SOM would compress these into a single output node that carries three weights.

If we happen to deal with a 20-dimensional dataset, the output node in this case would carry 20 weight coordinates.

Each of these output nodes do not exactly become parts of the input space, but try to integrate into it nevertheless, developing imaginary places for themselves.

![som](https://i.imgur.com/kDIxtVZ.png)

In simple terms, our SOM is drawing closer to the data point by stretching the BMU towards it. The end goal is to have our map as aligned with the dataset as we see in the image on the far right.

That's a long process, though. Right now we only care about that BMU. As you can see in the first image, the BMU (yellow circle) is the closest to the data point (the small white circle). As you can also see, as we drag the BMU closer to the data point, the nearby nodes are also pulled closer to that point.

Our next step would be to draw a radius around the BMU, and any node that falls into that radius would have its weight updated to have it pulled closer to the data point (row) that we have matched up with.

![som](https://i.imgur.com/xcgmHii.png)

The closer a node is to the BMU, the heavier the weight that will be added to in its update.

If we then choose another row to match up with, we'll get a different BMU. We'll then repeat the same process with that new BMU.

![som](https://sds-platform-private.s3-us-east-2.amazonaws.com/uploads/43_blog_image_30.png)

Sometimes a node will fall into both radii, the one drawn around the green BMU as well as the one around the blue BMU. In this case, the node will be affected more by its nearest BMU, although it would still be affected at a lesser degree by the further one.

If, however, the node is almost equidistant from both BMUs, its weight update would come from a combination of both forces.

**In visual terms, that would lead us to a map that looks something like this:**

![som](https://i.imgur.com/b21cIIa.png)



**There are a few points to bear in mind here:**

- **SOMs retain the interrelations and structure of the input dataset.**

The SOM goes through this whole process precisely to get as close as possible to the dataset. In order to do that, it has to adopt the dataset's topology.

- **SOMs uncover correlations that wouldn't be otherwise easily identifiable.**

If you have a dataset with hundreds or thousands of columns, it would be virtually impossible to draw up the correlations between all of that data. SOMs handle this by analyzing the entire dataset and actually mapping it out for you to easily read.

- **SOMs categorize data without the need for supervision.**

As we mentioned in our introduction to the SOM section, self-organizing maps are an unsupervised form of deep learning. You do not need to provide your map with labels for the categories for it to classify the data.

It develops its own classes.

- **SOMs do not require target vectors nor do they undergo a process of backpropagation.**

If you remember from our artificial neural networks section, the network would need to be provided with a target vector (supervision). The data then goes through the network, extract results, compare them to the target vector, detect any errors, and then backpropagate these findings in order to update the weights.

Since we have no target vector, seeing as how SOMs are unsupervised, there would consequently be no errors for the map to backpropagate.

- **There are lateral connections between output nodes.**

The only connection that emerges between the output nodes in an SOM is the push-and-pull connection between the nodes and the BMUs based on the radius around each BMU.

There is no activation function as with artificial neural networks.

You will sometimes see the nodes lined up in a grid, but the only function for that grid is to clarify that these nodes are part of an SOM and to neatly organize them. The grid does not connect the nodes.


## Training The Self Organizing Maps

![som](https://i.imgur.com/glC1zKA.png)


## Credit

**Coded By**

[Anupam Verma](https://github.com/anupam215769)

<a href="https://github.com/anupam215769/Fraud-Detection-SOM-DL/graphs/contributors">
  <img src="https://contributors-img.web.app/image?repo=anupam215769/Fraud-Detection-SOM-DL" />
</a>

[![linkedin](https://img.shields.io/badge/linkedin-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/anupam-verma-383855223/)


