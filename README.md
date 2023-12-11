# My_Own_Micrograd

You can see the colab notebook [here](https://colab.research.google.com/drive/1azRgZSXrYj0L3_bIfIheFhPZ04WEi74I?usp=sharing) .
This is inspired from Andrej Karpathy's first video of the Zero to Hero series. [here](https://www.youtube.com/watch?v=VMj-3S1tku0) is the link to the video
In this video he creates a neural network from scratch and trains it, also from scratch. <br>

![image](https://github.com/SamyakMahajan/My_Own_Micrograd/assets/118765670/ca76cc1b-074c-4a6e-839d-d93400a48da0)

On a Test I did this was the data used<br>
![image](https://github.com/SamyakMahajan/My_Own_Micrograd/assets/118765670/ca256ea9-b512-40d2-a151-6e94c5cbd9ef)

My Neural Net Was Able To Predict like this:<br>
![image](https://github.com/SamyakMahajan/My_Own_Micrograd/assets/118765670/8cb1b8e0-67db-43d6-af8f-26ef04201b2e)

<br>
I love how beautifully he has presented in the video. <br>
I didn't even know about the basics of ML, yet from the video I was able to understand:<br>
1. gradients<br>
2. how gradients are calculated efficiently using Backpropagation<br>
3. how these gradients can be used to reduce the total_loss<br>
4. What a Neuron is and how to code it.<br>
5. What a Layer is and how to code it.<br>
6. What a MultiLayer Perceptron Neural Network is and how to code it.<br>
7. How to use gradients to train the Neural Net<br>
And also, I learnt a lot about python programming too, mainly how he was able to make simple a+b and a*b operations into a complete tree structure!<br>
<br>
This is the Node structure that was used:<br>

![image](https://github.com/SamyakMahajan/My_Own_Micrograd/assets/118765670/125f36ff-ddc8-4160-8ba1-bb5f8266dfdd)


All the steps of how this neural net was implemented and trained(I am writing this so I don't forget later):<br>
<ol>
  <li>Create a Value class that has a data property and can perform basic operations like + and *</li>
  <li>Define Value such that whenever a new operation is done, it returns a new Value node which has the resultant data(for ex a+b) and also has properties that store the operation from which it came(self.op), and the nodes from which it came(self._children)</li>
  <li>We can now use this data about the nodes and form a graph that shows all the nodes whose result is the final node</li>
  <li>We now know the relation of each node with the end node, so we can see how much the final value changes if we change a node's value slightly. This change in the final value can be quantified by the calculus property of "gradient"</li>
  <li>We see that the children of the last node have some specific patterns when calculating gradient corresponding to the operation they performed by which we find rules of finding gradient without having to change the node values</li>
  <li>We also see that the total gradient of the children of the final node can be calculated as follows by a chain rule : gradient of this node for the next node* gradient of the next node for the final node.</li> 
  <li>In other words: if the final node is L, current node is a, its next node is b, then: dL/da=(db/da)*(dL/db). </li>
  <li>By using these rules, we can calculate the gradients of each node without having to change the values of any node.</li>
  <li>The chain rule allows us to calculate the gradients of the penultimate nodes, then of the previous nodes of the penultimate nodes and so on. This process is called Backpropagation</li>
  <li>Gradients have a property that moving towards the gradient values is the direction of the maximum growth of the final value L. Exactly for the same reason, moving towards negative gradient is the direction of fastest decrease</li>
  <li>
    If we define Loss as the square of the errors of predicted values - actual values, we can use this property to find the most appropriate model.   
  </li>
  <li>
    
  </li>
  <li>
    
  </li>
  <li>
    
  </li>
  <li>
    
  </li>
</ol>

