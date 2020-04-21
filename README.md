## Image Filter API
This is simple api that take image url from query string and return the resized image. Clean up all images from local storage after done processing.

### Setup Node Environment

You'll need to create a new node server. Open a new terminal within the project directory and run:

1. Initialize a new project: `npm i`
2. run the development server with `npm run dev`

### How to run
1.  Image url: https://1.bp.blogspot.com/-1uQRYMklACU/ToQ6aL-5uUI/AAAAAAAAAgQ/9_u0922cL14/s1600/cute-puppy-dog-wallpapers.jpg
2.  Endpoint url: http://udgram-image-filter-dev.us-west-2.elasticbeanstalk.com/filteredimage?image_url=

http://udgram-image-filter-dev.us-west-2.elasticbeanstalk.com/filteredimage?image_url=https://1.bp.blogspot.com/-1uQRYMklACU/ToQ6aL-5uUI/AAAAAAAAAgQ/9_u0922cL14/s1600/cute-puppy-dog-wallpapers.jpg

### How to deploy
#### Prerequisite

1.  Install eb cli.
2.  Install aws cli.
3.  Install nodejs

#### Deploy to AWS
```bash

    npm run build
    #create environment
    eb init
    #create application
    eb create
    #deploy
    eb deploy
```

#### Setting up aws env
    1. Go to Elastic Beanstalk.
    2. Click on the environmnt-application.
    3. Click on Configuration on the left.
    4. Scroll down for environment variable and type these in
        POSTGRESS_USERNAME=udagramadmin
        POSTGRESS_PASSWORD=udagrampassword
        POSTGRESS_DATABASE=udagram
        POSTGRESS_HOST=udagram.crmba6kvrbxw.us-west-2.rds.amazonaws.com
        AWS_REGION=us-west-2
        AWS_PROFILE=udagram
        AWS_BUCKET=udagram-knguyen-dev
        JWT_SECRET=somerandome

### Screen shots

#### Deployment
![eb deployment](deployment_screenshots/eb_screenshot.png "deployment")

#### Successful call from api on browser
![running example](deployment_screenshots/running_example_eb.png "deployment")

#### Successful call from api on postman
![running example](deployment_screenshots/running_example_postman.png "deployment")

#### Failed call from api due to invalid url.
![failed example](deployment_screenshots/failedcall.png "failed")