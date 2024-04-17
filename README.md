## Step to run MultiLanguage Invoice Extractor in local/windows
- Clone google-gemini in your local machine
- Download and install Anaconda from https://www.anaconda.com/download
- Type anaconda on windows search and open anaconda command prompt
- Navigate to mcqgen progect (in step 1) from conda prompt and/by follow below commands
    * cd <basepath>/google-gemini
    * conda create -n google-gemini python=3.11 -y
    * conda activate google-gemini
    * pip install -r requirement.txt
- Create a file with name '.env' in google-gemini folder
- Add below line in .env file
    * GOOGLE_API_KEY="<Supply your secret token here>"
- Run MultiLanguage Invoice Extractor with below command
    * streamlit run app.py --server.port 8080
    * Access the application on http://localhost:8080 from any of your favorite browser
    * Upload any png, jpg or jpeg invoice file of any language and in prompt ask any question e.g. what is the total bill?
    * Click on 'Tell me about the invoice' to extract the information.
## Step to run MultiLanguage Invoice Extractor in AWS EC2
- Login to the AWS: https://aws.amazon.com/console/
- Search for EC2 service
- Choose UBUNTU Machine
- Launch EC2 instance
- Run below command to update teh OS
     * sudo apt update
     * sudo apt-get update
     * sudo apt upgrade -y
     * sudo apt install git curl unzip tar make sudo vim wget -y
     * sudo apt install python3-pip
     * git clone git@github.com:ThirdEyeInfo/google-gemini.git
     * cd google-gemini
     * pip3 install -r requirement.txt
- Add GOOGLE_API_KEY with value in .env file
     * vi .env
     * Click 'insert' button and add below line
     * GOOGLE_API_KEY="<Supply your secret token here>"
     * Click on 'escape' button and type ':wq!' to save the file and exit
- To run the application execute below command
     * python3 -m streamlit run app.py --server.port 8080
- To make 8080 port accessible from public domain navigate to EC2->Network & Security->Security Groups->Security group ID (click on your security group id)
- This will open a new page, from here click on 'Edit inbound rules' button
- This again will open a new page where you can click on 'Add rule' button and follow below instructions
     * Type == Custom TCP
     * Port range == 8080
     * Source == don't select anything from dropdown instead click on 'search bar' and select '0.0.0.0/0'
     * click on 'Save rules' button and the bottom of the page and access it using 'Public IPv4 address' which is located under EC2->Instances->(instance id)
     
          
  
