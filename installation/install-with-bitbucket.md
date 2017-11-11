# Install Drone with Bitbucket

## How to register OAuth application

Go to your account setting in bitbucket, click `OAuth` under `ACCESS MANAGEMENT` menu on left sidebar and click `Add consumer` under `OAuth consumers`.

<img src="images/bitbucket-setup-01.png" />

You will see the following register page.

<img src="images/bitbucket-setup-02.png" />

Please make sure that your drone `Callback URL` setting. It is very import the authorization callback URL matches your http(s) scheme and hostname exactly with **/authorize** as the path.

<img src="images/bitbucket-setup-03.png" />

Check the following OAuth Permissions

<img src="images/bitbucket-setup-04.png" />

Copy `Key` and `Secret` in `OAuth consumers`，Open your drone home page in your browser and login as BitBucket account.

<img src="images/bitbucket-setup-05.png" />
