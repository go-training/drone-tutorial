# Install Drone with Bitbucket

See the online documentaion:

* Bitbucket Cloud: [Single Machine](https://docs.drone.io/installation/bitbucket-cloud/single-machine/) | [Multi-Machine](https://docs.drone.io/installation/bitbucket-cloud/multi-machine/)
* Bitbucket Server: [Single Machine](https://docs.drone.io/installation/bitbucket-server/single-machine/) | [Multi-Machine](https://docs.drone.io/installation/bitbucket-server/multi-machine/)

## How to register OAuth application

Go to your account setting in bitbucket, click `OAuth` under `ACCESS MANAGEMENT` menu on left sidebar and click `Add consumer` under `OAuth consumers`.

![bitbucket-setup-01](images/bitbucket-setup-01.png)

You will see the following register page.

![bitbucket-setup-02](images/bitbucket-setup-02.png)

Please make sure that your drone `Callback URL` setting. It is very import the authorization callback URL matches your http(s) scheme and hostname exactly with **/authorize** (0.8) **/login** (1.0) as the path.

![bitbucket-setup-03](images/bitbucket-setup-03.png)

Check the following OAuth Permissions

![bitbucket-setup-04](images/bitbucket-setup-04.png)

Copy `Key` and `Secret` in `OAuth consumers`

![bitbucket-setup-06](images/bitbucket-setup-06.png)

Open your drone home page in your browser and login as BitBucket account.

![bitbucket-setup-05](images/bitbucket-setup-05.png)
