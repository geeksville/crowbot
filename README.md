# crowbot

A machine driven bot for training animals (initially the loud but supposedly smart crows outside my house)

## Required hardware

* A [Google Coral dev board](https://coral.withgoogle.com/docs/dev-board/get-started/).  This is a really cool board which provides hardware acceleration for their TensorFlow machine learning models.  I'll try to use this project as a meaty test/example of what that board can do.
* A 3D printable feeder with associated servo. (Not yet available, will likely be based on [this](https://www.thingiverse.com/thing:3269637))
* A feeding platform (approximately 4' x 4' of plywood, painted white)
* A pullcord (that the crow pulls to request new food - needed for the 4th challenge - see below)

## Implementation plan

But my rough plan is (I'll keep a running public write-up on the progress in a nice markdown that goes with the git code / feeder model)

* Convert my existing 3d printed rpi based cat feeder pwm stepper to be driven from a coral gpio.  Possibly also reuse bits from my [hummingbird recognizer Twitterbot](https://github.com/geeksville/hummingbot). Post updated feeder and Coral case/mount to [my Thingverse repo](https://www.thingiverse.com/punkgeek/about).
* Install feeder on my deck with the coral camera looking at a white background where the feed is dispensed and the crow is expected to stand (and eventually interact)
* Initially dispense a small amount of food periodically - to ensure ready bait for any bird (I have lots of crows in my neighborhood but want to start easy)
* Use the sample recognizer + current image has at least low confidence of bird + "save current image to disk/emit a little new food 5 min from now (to allow current bird only one feeding at a time and avoid scaring them due to machine noises"
* Use images from previous step to build a curated corpus of: not bird vs not crow vs crow buckets.  I'll use the Coral/Tensorflow documentation to somehow convert that corpus into a custom model for my application.
* Change to only feeding crows
* First crow challenge: if the crow stays at the feeder, keep dispensing food. (Advance to new challenges as my crows learn - adjust challenges as needed)
* 2nd challenge: only keep dispensing food if the crow stands in a certain marked area of the target
* 3rd challenge: no longer 'prime the pump' with free food.  Instead dispense only if the crow stands on the target
* 4th challenge: after initial food only keep dispensing if the crow Pulls the string at the target (connect to gpio)

So that's my rough plan - any feedback is welcome.

## Schedule

I'll be writing the first version in November (in this github) and then iterating with my black winged test subjects through the winter and spring.
If you'd like to contact me, I'm kevinh@geeksville.com.
