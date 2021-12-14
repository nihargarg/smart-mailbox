# Intelligent and Connected Mailbox
A project by Rohan Raghuraman, Anhadveer Khokar and Nihar Garg
For the Internet of Things (IoT) course at Columbia University in the City of New York

https://youtu.be/owcQavW3YhE

### What:
- We aim to create an Intelligent and Connected Mailbox (ICM) that can read the handwriting off an envelope and determine whether the mail has reached the correct person.
- If it is correct, it will notify the user that they have new mail and even attempt to categorize it for better organization.
- If it is incorrect, it will reject the mail and notify the deliverer to return the mail to its sender.

### Why:
- The ICM is a consumer-facing device that not only improves efficiency and organization, but also helps secure your mail and prevent robbery by instantly notifying the user when they have new mail.
- Very often we come across mail that wasn’t sent to the right address or mail that was meant for older tenants who have moved home since. Instead of having to forward the wrong mail ourselves, the ICM can inform the deliverer of its incorrectness without having to bother the consumer.

### Who:
- The product’s market can be targeted towards suburban or rural households where each homeowner wouldn’t purchase a large device like Amazon Hub.
- It can also be a great help towards elderly people or people with various disabilities or sensory impairments by being able to notify them when they get new mail, so they don’t have to check for mail everyday. It will also help categorize the mail for them and send back any incorrect ones.

### How:
- **Embedded Systems**: The integration of a Raspberry Pi microprocessor, a light dependent resistor (LDR) for sensing presence of a letter, a camera to click an image, and a servo motor to actuate a platform to accept/reject mail.
- **Computer Vision**: An Optical Character Recognition (OCR) algorithm to transform an image of the envelope, recognize words in the image and convert them to text, and try various enhancements on image until a valid name and address is determined.
- **Supervised Machine Learning**: A k-nearest neighbors (kNN) classifier algorithm with an accuracy of 92% predicted the category (spam/ham) that the mail sender belongs to. If not spam, an SMS message is sent using the Twilio messaging API to notify the user of a new mail.
- **Data Visualization on the Cloud**: The user also receives a link to an online data visualization where they can access any trends and make inferences from the data. Some examples of graphs were total number of mails per day and percent of mails that are spam.

### Feature List:
| Feature | Description |
| --- | --- |
| 1) Mail Detection | Detect that a new mail was inserted into the mailbox and click a picture |
| 2) Optical Character Recognition | Process the image using openCV and read the text on the envelope |
| 3) Correct Delivery Checker | Determine if receiver name on the envelope matches the name of the mailbox owner, and returns envelope to mailman if not <sup>[1]</sup> |
| 4) Mail Categorizer | If mail was accepted, use ML model to categorize and label mail as Spam/Ham |
| 5) Smartphone Notifier | If mail is not spam, then send an SMS to user's smartphone with sender's name |
| 6) Data Visualizer on the Cloud | Show data trends over time such as percent of spam mail, time of day mail is delivered, and number of mails currently in mailbox |

<sup>[1]</sup> We assume the mailman has delivered the mail to the right address so we do not compare receiver address to mailbox address, but we are checking receiver's name in case the mail is addressed to a previous resident who no longer lives at the address.
