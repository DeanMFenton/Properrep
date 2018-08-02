# Cleeng Sandbox

After tutorial 1 and 2 you should know the basics of our PHP SDK, how to protect content and how to create offers. As you probably have seen there was no option explained yet to test payment process without using real cash.

In this Tutorial, you can learn how to work on our test server Cleeng Sandbox.

Next to be able to experiment around without real money involved, it is wise to use the sandbox to avoid your real reporting (and statistics) are "messed-up" with your test data.
## 1. Introduction

You have to realize that Sandbox works on totally different database, so to start with you have create a separate account:

1. Register a publisher account sandbox registration
2. Get your new Publisher Token from sandbox api-keys

Note: when you switch between servers, think about deleting the cookies in your browser to avoid any conflicts.
## Let's build a sand castle
### 2.1 Creating new offer via Sandbox

As you can see, everything we are doing here is exactly the same but in a different environment. Let's have a look at create_offer.php

To create offers on Sandbox, you have to:

1. Set new publisherToken from Sandbox

` $publisherToken = 'YOUR_SANDBOX_PUBLISHER_TOKEN';`

which you can find in sandbox api-keys.

     
2. Set endpoint to sandbox.

    By default in `Api.php` you can find:

    `protected $endpoint = 'https://api.cleeng.com/3.0/json-rpc';` these are production servers

    To set new endpoint, after you create a new API object you just have to add

    `$cleengApi->enableSandbox();`

    Like this:  

``` 
    $cleengApi = new Cleeng_Api();
    $cleengApi->setPublisherToken($publisherToken);
    $cleengApi->enableSandbox();
```
That's it! Now, you can create offers on Cleeng Sandbox platform.
# 2.2 Protecting offer on Sandbox
Changes you have to make in purchase.php:

1.Set `offerId` that you created using Sandbox.

2.Add `$cleengApi->enableSandbox();`
     
```
    $cleengApi = new Cleeng_Api();
    $cleengApi->enableSandbox();
```
That's it!
# 3. So, what has changed?

Ok, now if you click on your Buy-Button (or link), and after you log in (not on current content publisher account, please create different one) you can choose Credit Card payment method. Enter below details in order to purchase for free!

Payment data:

* Card number: 5555 4444 3333 1111
* Card name: any
* Card date: 08 / 2018
* CVC: 737

Done, you are able to test the whole process of protecting and selling with Cleeng.
