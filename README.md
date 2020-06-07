# COVID-19-Xray-Detection
Detecting COVID-19 in X-ray images with Keras, TensorFlow, and Deep Learning

The Code shows on How to automatically detect COVID-19 in a hand-created X-ray image dataset using Keras, TensorFlow, and Deep Learning.

Like most people in the world right now, I’m genuinely concerned about COVID-19. I find myself constantly analyzing my personal health and wondering if/when I will contract it.

Sample an open source dataset of X-ray images for patients who have tested positive for COVID-19
Sample “normal” (i.e., not infected) X-ray images from healthy patients
Train a CNN to automatically detect COVID-19 in X-ray images via the dataset we created
Evaluate the results from an educational perspective


In the first part of this tutorial, we’ll discuss how COVID-19 could be detected in chest X-rays of patients.

From there, we’ll review our COVID-19 chest X-ray dataset.

I’ll then show you how to train a deep learning model using Keras and TensorFlow to predict COVID-19 in our image dataset.

COVID-19 tests are currently hard to come by — there are simply not enough of them and they cannot be manufactured fast enough, which is causing panic.

When there’s panic, there are nefarious people looking to take advantage of others, namely by selling fake COVID-19 test kits after finding victims on social media platforms and chat applications.

Given that there are limited COVID-19 testing kits, we need to rely on other diagnosis measures.

For the purposes of this tutorial, I thought to explore X-ray images as doctors frequently use X-rays and CT scans to diagnose pneumonia, lung inflammation, abscesses, and/or enlarged lymph nodes.

Since COVID-19 attacks the epithelial cells that line our respiratory tract, we can use X-rays to analyze the health of a patient’s lungs.

And given that nearly all hospitals have X-ray imaging machines, it could be possible to use X-rays to test for COVID-19 without the dedicated test kits.

A drawback is that X-ray analysis requires a radiology expert and takes significant time — which is precious when people are sick around the world. Therefore developing an automated analysis system is required to save medical professionals valuable time.

Note: There are newer publications that suggest CT scans are better for diagnosing COVID-19, but all we have to work with for this tutorial is an X-ray image dataset. Secondly, I am not a medical expert and I presume there are other, more reliable, methods that doctors and medical professionals will use to detect COVID-19 outside of the dedicated test kits.

The COVID-19 X-ray image dataset we’ll be using for this tutorial was curated by Dr. Joseph Cohen, a postdoctoral fellow at the University of Montreal.

One week ago, Dr. Cohen started collecting X-ray images of COVID-19 cases and publishing them in the following GitHub repo.

Inside the repo you’ll find example of COVID-19 cases, as well as MERS, SARS, and ARDS.

In order to create the COVID-19 X-ray image dataset for this tutorial, I:

Parsed the metadata.csv file found in Dr. Cohen’s repository.
Selected all rows that are:
Positive for COVID-19 (i.e., ignoring MERS, SARS, and ARDS cases).
Posterioranterior (PA) view of the lungs. I used the PA view as, to my knowledge, that was the view used for my “healthy” cases, as discussed below; however, I’m sure that a medical professional will be able clarify and correct me if I am incorrect (which I very well may be, this is just an example).
In total, that left me with 25 X-ray images of positive COVID-19 cases (Figure 2, left).

The next step was to sample X-ray images of healthy patients.

To do so, I used Kaggle’s Chest X-Ray Images (Pneumonia) dataset and sampled 25 X-ray images from healthy patients (Figure 2, right). There are a number of problems with Kaggle’s Chest X-Ray dataset, namely noisy/incorrect labels, but it served as a good enough starting point for this proof of concept COVID-19 detector.

After gathering my dataset, I was left with 50 total images, equally split with 25 images of COVID-19 positive X-rays and 25 images of healthy patient X-rays.

I’ve included my sample dataset in the “Downloads” section of this tutorial, so you do not have to recreate it.

Additionally, I have included my Python scripts used to generate the dataset in the downloads as well, but these scripts will not be reviewed in this tutorial as they are outside the scope of the post.
