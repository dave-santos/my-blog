---
title: "Complete Guide To Safely Store Recovery Words of Crypto Wallets"
date: 2018-05-02T05:14:31Z
tags:
  - blockchain
---

Crypto wallet comes with recovery words where you can recover
the wallet if somehow you lost it. In a way, **the recovery words is a secret
that you should protect just as much as the wallet itself**. 
This brings a confusion
on how to store it due to its importance and vulnerability.
But no worry, this guide will walkthrough you on how 
to keep the recovery words 🤘 👌 .

## Requirements

1. **Everlasting**. most of us want the recovery words which will last for our life time.
Since the average age of crypto investors are in 20s[1] and life expectancy is around 80[2] years old
it means we want some storing method that would last for at least 60 years old 👴🏻.
2. **Safe**. It's important to keep it where no one can see it and even somecan can see it, it's not easy 
for that person to get the secret.
Therefore we need to have a method to split our secret into multiple parts/shares. It's also important
that each share won't leak any information whatsoever on the secret. So a simple divide-the-secret 
into-multiple-parts technique won't cut it.
3. **Comprehensible**. Imagine in 2078, you want to open your wallet with the secret in hand. 
But somehow, somehow.. you can't use the damn secret! You can't access your own coins!
The young you used a customized complex shuffling algorithm 
created by only you that you can't even remember because 
you are already old. Or it's in a device which uses an ancient file storing system that can't be read
by your iPhone 70s. Or many other reasons.. So it's important to store the secret in a comprehensible
and known method so the old you can understand it.

## The Solution 

### Step 1. Split The Secret!

The best method to split a secret is by a secure and well-known algorithm
called as Shamir's Secret Sharing (SSS)[3]. With SSS, you can
encrypt your secret into multiple shares where each share 
alone won't leak any information on the the secret. Another great thing 
is, if you want, it's still possible to reconstruct the secrets if one share
is missing! 

With SSS, you can configure 
(1) how many shares your secret will be 'splitted' into and 
(2) the minimum number (threshold) of shares to recontruct the secret.
In my view, it's better to have the secret to be splitted into 3 shares
and it's possible to reconstruct by at least 2 shares. 
I chose these numbers because of the availability of medium where 
we can store it and also
as an emergency if one of the shares is missing. We will see that in next section.

Since SSS is a famous algorithm, it's very likely that
it'll last for centuries. It was created in 1979 and it's still
around until now. You can pretty sure you will be able to reconstruct
the secret with internet of the future.

It's tempting to use more than one algorithms or 'switching some words' which only known by you.
But remember that even 10 years from now, there's a possibility that 
you will forget the combination of algorithms. Furthermore, it's sufficient to use
an algorithm as strong as SSS.

#####  Example

Let say you have these 12 words as the secret:

> witch collapse practice feed shame open despair creek road again ice least

Should you really encrypt all the words? Not really, it's still safe to
only encrypt half of it. It will take centuries to guess the rest even with a supercomputer.
Is your wallet worthy enough for someone to rent a supercomputer and run it for centuries? 
Most likely not 😏! 
However if you are still not comfortable, 
you can still encrypt all words, no problem. Some wallets have more than 12 words, 
thus encrypt at least half of them not less.

We can remove all spaces and only 
use the first 4 letters in each word (recovery words are unique until 4th letter).
Also use camel case to distinguish the words.
So in our example it'll be:

> DespCreeRoadAgaiIceLeas

The best tool in the internet right now to use SSS 
algorithm is at [PassGuardian.com](http://passguardian.com/).
It works offline, so you can save it and store it in your own computer.
From the website with the configuration of 3 shares and 2 threshold I got:

> 801114051a8...
8023739d1a9...
8032779ffae...

In here I truncated the shares for brevity and it's possible to have
different shares from what I have here. With these, you can store your shares in these forms:

> WitcCollPracFeedShamOpen+801114051a8..
WitcCollPracFeedShamOpen+8023739d1a9..
WitcCollPracFeedShamOpen+8023739d1ae..

If you easily forget things, it wouldn't hurt to put the method in each shares like this:

> WitcCollPracFeedShamOpen+SSS(8023739d1ae..)

### Step 2. Store the Shares!

Now when you already have the shares, where should you put it? 
These are the three places to store the shares:

1. **The Cloud**. You can put the first share in your Google Drive, Dropbox, or Box. 
Yeah I know, there's a big chance that they will discontinue their 
services in the next 60 years. But when it happens, you will migrate all your files in that service right?
I know for sure if Dropbox goes bankrupt, I won't stay silent and let all my files got deleted by them. 
I will definitely move all my files (including the share) to another service. It's also safe to 
put *the same share* to more than one cloud services. Remember it has to be the same share! 
So even though your laptop got stolen, and the thief
has access to all of your cloud accounts, the thief can't reconstruct the secret because 
they are the same share!
2. **The Paper**. It's old school but it works! Ask historians how they got most stories from the ancient time? 
Yeap, by ink and papers! Putting in a USB/SSD/Hard drive is enticing but remember how advanced the technology will be in
60 years. Imagine if your grandfather now ask you to extract a file from an 8-inch floppy disk 🤣 !
Write down the second share in a paper.
Make a few copies of *the same share* and put them in safe and private places.
3. **The Blockchain**. Data in blockchain is permanent, it's forever! 
So it's also an appropriate place to put something which meant to last for a long time!
By that logic, you can put the third share in blockchain!
But remember, blockchain is a public space,
everyone can read it! 
So, the best thing to do is to encrypt the 
data before storing it to blockchain. 
I've made an app which allow you to do exactly that! It's in [NoteChain.org](https://notechain.org).
It's using the famous, standar, and secure encryption method called as AES-CTR 
mode with SHA-256 as the hashing algorithm[4]. 
Notechain is a decentralized application running on Ethereum, so even though 
someday NoteChain is out of service, the encrypted data is still 
safe and secure in blockchain.
Of course you can use another app outside of NoteChain.
Just be aware to use a long encryption time and a strong password when storing the share to blockchain.

Putting the shares in these 3 places is very safe and secure. 
Let me remind you that even tough one share is read
by someone, that someone won't be able to get not even a single encrypted word!
No need to worry if a bad employee from Google Drive will peek at your files, get your secret, and 
steal your coins. It won't happen.

### Step 3. Try to Reconstruct it!

Now, before your burn your recovery seeds paper, it's the best to try to reconstruct
it just in case you made a mistake. If you did,
try to split the secret fresh again from the very beginning. It will be the best if you do 
this step on different day from step 1 and 2 to simulate the 'real' situation of reconstruction.

### (Optional) Remember few words

An average human is capable of remembering 2-4 words pretty easily so it's not outside of the realm of 
possibility if you want to remember at least the first two encrypted words. Based on the 
example, we should remember these two words:

> despair creek 

How we can remember this for decades? A good way is to use this as your password!
For example, use *"DespCree18!"* as the password for your twitter or facebook.. 🤫

Why we are doing this step? This is just in case if somehow you could only find one share! 
Shit could happen!
Remembering the first two words will make guessing the rest of the words 
possible in probably under a year: not cheap but all hope is not lost! 

## Conclusion

Alright, I've presented my solution in storing the recovery seeds of crypto securely and safely.
Now you can sleep well at night knowing that your secret is safe ☺️ 

What do you think? Do you have any comments or suggestions? Let me know! 

## References

[1] <https://news.bitcoin.com/survey-finds-south-korean-youth-the-most-active-crypto-investors/>

[2] <https://en.wikipedia.org/wiki/Life_expectancy>

[3] <https://en.wikipedia.org/wiki/Shamir%27s_Secret_Sharing>

[4] <https://notechain.github.io/#/about>
