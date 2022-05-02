# MLOps-AIOps

Empowering ML Work-Flow with DevOps within a MicroService Architecture and Deploying it in a Hybrid-Multi Cloud, maintaining CI/CD Pipeline: An OpenShift Orchestration of ML-OPS
Harvinder Singh Khalsa, Vedant Bhatt,
Yeshika Saini, Satish Alaria
Dept. of Information Technology, Arya Institute of Engineering and Technology, Kukas, Jaipur, India
{harvindersinghdiwan,vickyvedant365,yashikasaini78,satish.alaria}@gmail.com
Abstract— Machine Learning happens to be one of most used cutting edge technology in present era. The heart of any Machine Learning application is actually the ML model. A ML model is basically a file, which is an outcome of training over a datasets, done so as to recognize various sorts of patterns. Training the model involves different steps which is known as ML Workflow. This workflow involves manual interaction for various purposes and one such purpose is  hyper-parameter tuning. This manual interaction bring a lot of delay in production of ML based application in industries which is absolutely not tolerable. This issue is similar to the software development issue which was resolved by adopting DevOps workflow. DevOps works on automation of processes as much as possible by using automating tools and reduces the human interaction at every possible point. By integrating DevOps with ML workflow, we can achieve automation in ML pipeline for creating models and further it can also be extended till deployment and monitoring. In our research, we did an in-depth anatomy of ML workflow and tried to inspect every single point where we can bring automation and successfully minimized human interaction. Ultimately, we ended up modelling a ML-Ops based application encrypting it end-to-end with DevOps. For instance, in our project, we made a heart disease predictor model and deployed it in a hybrid multi cloud and orchestrated it using RedHat OpenShift.

Keywords— CI/CD (Continous Integration / Continous Deployment and Delivery), AWS (Amazon Web Services), GCP (Google Cloud Platform)
.
1.Introduction

There are certain steps involved in training a machine learning model [1]. These includes supplying the training data, training the ML algorithm, hyper-parameter tuning and validating and testing the model. Fig1 shows the steps very clearly. So far so good, but in real world we set a certain threshold value of accuracy for a given model below which the model is again trained from beginning. If the model gives accuracy below expected value, it is again retrained. And hyper-parameter  tuning [3] plays a great role in this. Hyper-parameters [2] are arguments that a machine algorithm accepts to tweak the models. For example, the k in k-nearest neighbour and the  


learning rate in neural network  is a hyper-parameter. This hyper-parameter tuning is of-course to be done manually by following a hit and trial approach. This hit and trial approach requires a lot of assumptions and calculations. This is uncertain for an instance and hence time consuming. Due to this a continuous flow in the ML workflow could not be achieved. But if we could automate this process of hyper-parameter tuning by using some automation tools then this can reduce time complexity and a continuous flow in ML workflow can be achieved. A solution is DevOps [4]. DevOps has tools that can automate this. DevOps itself works on automation and if we integrate Ml with DevOps then not only ML workflow can be automated , but deployment of ML based application can also be completely automated there by achieving a complete end-to-end CI/CD .  


Fig. 1: A figure showing ML WorkFlow

In our project, we trained a heart disease prediction model using various ML algorithms viz- K-Nearest Classifier, Random Forest Classifier, Support Vector Classifier and Decision Tree Classifier  [5], [6], [7], [8] and automated the hyper-parameter tuning as well as the comparison of models and then selected the best among all automatically as the final model. We then containerized the model in docker container for so as to achieve microservice application architecture  Then we deployed the application over AWS,GCP and RedHat OpenStack [9] giving it a hybrid multi cloud deployment architecture and finally orchestration was done by using RedHat OpenShift.

2.DevOps WorkFlow

DevOps comprises of two technical words - Development and Operations. DevOps is basically a thought process which aims to automate the development and operations in a software development industries. Traditionally, SDLC [10] approach for software development was followed which was too slow and took months and years for an application to get developed and delivered. But with DevOps, agility is achieved which makes it possible for industries to deliver applications within a few week or even days. Fig. 1 shows the DevOps workflow.


Fig. 2: A figure showing DevOps workflow
Software development lifecycle has eight fundamental phases. They are planning, coding, building, testing, releasing, deploying, operating and monitoring. DevOps brings agility by reducing the human interaction in these fundamental processes by automating wherever possible so that more focus can be put in areas of actual need like planning and coding. Automation is achieved using automating tools in every step. Tools such as Github and Bitbucket are for source code management in the first stage; Delphix for data virtualization; Jenkins, Team City , etc for CI/CD Pipeline; Selenium, Jira for testing; Ansible for configuration mangement and Terraform for resource provisioning; docker for containerization and Kubernetes and Openshift for orchestration; AWS , GCP for public cloud outsourcing and Openstack, OpenNebula for Private cloud self service; ELK stack (Elastic Search , Logstash and Kibana  for log monitoring) and finally Prometheus and Grafana for metrics monitoring. 
3.MLOPS WorkFlow
The pipelines in production require a agile and instant refurbishment, which can basically be achieved using CI/CD pipeline following a DevOps approach. This CI/CD can also be brought in Machine Learning workflow so that a continuous integration of feature engineering, hyper parameter tuning and model training can be done. 
The diagram below shows integration of DevOps in Machine Learning workflow which brings us a CI/CD Machine Learning Pipeline famously known as MLOPS.

Fig. 3: A figure depicting MLOPS
Following stages are involved in a pipeline:
1. The very first stage consists of the development and experimentation where different machine learning algorithm are tested to make a model and selecting a perfect fit algorithm for model creation. 
2. The second stage consists of the continuous integration of pipeline and hyper parameter tuning in an automated environment.
3. The third stage consists of continuous delivery of the pipeline where, the model after completeing the training stage, is deployed to the testing environment such that testing of the product is done before actual deployment in production server.
4. The fourth stage consists of continuous delivery of model in the production environment.
5. The fifth stage is all about monitoring and collecting metrics and  statistics on how the model is performing. The result of this stage happens to be a trigger which is used in execution of the pipeline.

Fig. 4: A figure showing stages of a pipeline
3.1 Continuous Integration
The continuous integration of the CI is where the bulding, testing and packaging is done when the new code is pushed into the source code management system (GIT/GITHUB) is done. Along with building packages, building container images and executable files, the CI phase also includes a number of tests which is listes below. 
1.Performing unit tests over your logic on which you have done feature engineering
2..Performing unit tests on different functions which you have used in your model.
3.Performing tests for aasssuring that there is an decrease in the loss.
4.Performing tests for NaN.
5.Performing tests to assure that the pipeline is producing expected results.
6.Performing tests to assure that the components in the pipeline are well integrated.
3.2 Continuous Delivery
Here in this phase, the designed pipeline delivers the output to the desired environment be it a testing environment or production environment where the so generated model is ussed to predict desired inputs. The following points are to be kept in mind for continuous delivery:
1.The compatiblity of the model with the desired infrastructure on which it is supposed to be deployed, must always be verified.
2.The expected outputs against a given input must always be tested by fetching a get request to the API of the service.
3.We must check that upon pushing a code to sourcce code repository, the a complete CI/CD is triggered.
4.We must also check that upon merging a peer reviewer’s code to the main branch, a trigger is generated to deploy the changed code the pre-production/ testing environment.
5.Once everything is tetsed, manually deploying the product to the production environment.
A complete CI/CD based Machine Learning application deployment environment or setup can be graphically visualized as shown in figure 

Fig. 5: A figure showing DevOps lifecycle
Proposed Idea
Our idea is basically to bring automation in the development and deployment of Machine Learning based applications and reduce human interactions in the process, unlike the traditional approach which was prominently manual. Doing so we can not only reduce the time consumption, but also get efficient models for real world use cases.
Methodology
The methodology we used can be broadly divided into 3 parts.
1.Automating ML Pipeline 
The ML Pipeline  is composed of certain steps and the most critical step is training the model with best accuracy. To do this a ML model has to be trained against a sets of training data and tested against a sets of testing data. This also involves the hyper-parameter tuning with accurate magnitude. Since this is a hit and trial method, the hyper-parameter tuning, training and testing has to be repeated a number of times until we achieve a desired accuracy of the model. This repetition was traditionally done with human interaction which caused time consumption. So the very first step in-order to achieve MLOPS, we in our research automated this process which reduced the cumbersome of manually tuning the hyper-parameters and thereby reducing time consumption.
2.Automating the Selection of Best-Fit ML Algorithm 
A ML model can be created using multiple different algorithms. For instance, a classification based problem can be solved using k-nearest neighbour as well as logistic regression [11] and a regression based problem can be solved using linear regression [12] as well as PCA [13]. However, the algorithms which best suits for a particular dataset is to be selected as final model for deployment. Traditionally, the selection of algorithms was done by training a model with multiple algorithms and comparing the accuracy among each. This again, due to the involvement of human beings, brought delay in the production of application. We in our research aim to automate this process using DevOps and remove the human interaction and achieve efficiency as well as save time.
3.Automating deployment of model in testing and Production environment
A testing environment is where you test your application before you actually give it to your clients and a production environment is where you finally deploy your application, wehrein your clients can interact with the application and make use of it. The traditional process of deploying a ML application was again manual. And its fine as far as small scale applications are developed. But current era is the age of AI. Applications are deployed in large scale. Automation must be introduced. We did the same and improved the deployment part.
The Project
In this project, we engineered a MLOPS Pipelined architecture to train a classification based machine learning model which is automated to tune the hyper-parameters. Four such pipelines are made, each for K-Nearest Neighbour, Decision Tree Classifier, Random Forest Classifier and Support Vector Classifier. The models so generated are tested against a set of testing datasets and the accuracy so calculated is compared among one another and the algorithm with highest accuracy is selected automatically for deployment with applications. Further, we also automated the operations part such as configuration management and monitoring so that a complete DevOps approach is practised.
The continous integration of ML Pipeline for training the model
In this part, we used jenkins to automate the continous integration of training pipeline. The figure shows a schematic diagram of  the same.

Fig. 6: A figure showing CI of ML pipeline
The Deployment architecture
The deployment architecture is shown in figure 7. The deployment architecture basically describes how the apllication that we made is acually to be deployed. We in our project, while training and testing the heart disease predictor model, empowered DevOps so that a CI/CD is seen. And we also containerized it such that we can actually give it a microservice architecture. And the final phase is to deploy and orchestrate it.
The deployment architecture can be explained as follows:
1.Pushing the final code to github
2.Automating the building of container image using buildah 
3.Automating push of the built image to image repository, docker hub in our case.
4.Automating the provisioning of infrastructure in AWS, GCP, Openstack and Azure using terraform, having compatiblity to deploying an OKD cluster [14]
5.Automating the configuration of OKD multinode cluster in AWS using Ansible .
6.Automating the configuration of pod deployment configuration in openshift using ansible.
7.Automating the deployment of pods using the images pushed in step 3.
8.Finaly, orchestrating the application, which is to be done by an openshift administrator and openshift developer manually.  

Fig. 7: A figure showing deployment architecture of the MLOPS application that would finally predict the hheart disease.

Conclusion

We’ve successfully implemented a machine learning application that would predict a heart disease. And to achieve this, the approach which we used was a CI/CD pipeline based on DevOps, thereby empowering Machine Learning workflow with DevOps. This gives us a facility to automatically test and deploy new pipeline if we tend to do so in future.
 
References
     
[1]	Shireesha Chintalapati, M.V. Raghunadh, “Automated Attendance Management System Based On Face Recognition Algorithms”, 2013 IEEE International Conference on Computational Intelligence and Computing Research.

[2] Mercy Prasanna Ranjit; Gopinath Ganpathy;Kalaivani Sridhar; Vikram Arumugham; “Efficient Deep Learning Hyperparameter Tuning Using Cloud Infrastructure: Intelligent Distributed Hyperparameter Tuning with Bayesian Optimization in the Cloud”, 2019 IEEE 12th International Conference on Cloud Computing (CLOUD).

[3] Antonino A. Feitosa Neto;João Carlos Xavier;Anne M.P. Canuto;Alexandre C.M. Oliveira, "Automatic Parameter Tuning using Bayesian Optimization Method,"2019 IEEE Congress on Evolutionary Computation (CEC).

[4] Abubaker Wahaballa;Osman Wahballa;Majdi Abdellatief; Hu Xiong;Zhiguang Qin; “Toward unified DevOps model” 2015 6th IEEE International Conference on Software Engineering and Service Science (ICSESS).

[5] Qiang Hua;Aibing Ji;Qiang He; "Multiple Real-valued K nearest neighbor classifiers system by feature grouping" 2010 IEEE International Conference on Systems, Man and Cybernetics

[6] Purushottam; Kanak Saxena; Richa Sharma; "Efficient heart disease prediction system using decision tree" 2015 International Conference on Computing, Communication & Automation

[7] Yeshvendra K. Singh; Nikhil Sinha; Sanjay K. Singh; "Heart Disease Prediction System Using Random Forest" 2016 International Conference on Advances in Computing and Data Sciences
[8] Thanh-Nghia Nguyen;Thanh-Hai Nguyen;Duc-Dung Vo;Truong-Duy Nguyen “Multi-class Support Vector Machine Algorithm for Heart Disease Classification” 2020 5th International Conference on Green Technology and Sustainable Development (GTSD)

[9]What is RedHat OpenStack? Accessed On: 29/03/2021 [Online] Available: https://www.redhat.com/en/technologies/linux-platforms/openstack-platform

[10]  S, Shylesh, A Study of Software Development Life Cycle Process Models (June 10, 2017). Available at SSRN

[11] Alzen, J.L., Langdon, L.S. & Otero, V.K. A logistic regression investigation of the relationship between the Learning Assistant model and failure rates in introductory STEM courses. IJ STEM Ed 5, 56 (2018).

[12] Panchenko D. 18.443 Statistics for Applications, Section 14, Simple Linear Regression. Massachusetts Institute of Technology: MIT OpenCourseWare; 2006.

[13] S. Sehgal, H. Singh, M. Agarwal, V. Bhasker and Shantanu, "Data analysis using principal component analysis," 2014 International Conference on Medical Imaging, m-Health and Emerging Communication Systems (MedCom), 2014, pp. 45-48, doi: 10.1109/MedCom.2014.7005973.

[14] Bjørgeengen J. (2019) A Multitenant Container Platform with OKD, Harbor Registry and ELK. In: Weiland M., Juckeland G., Alam S., Jagode H. (eds) High Performance Computing. ISC High Performance 2019. Lecture Notes in Computer Science, vol 11887. Springer.
