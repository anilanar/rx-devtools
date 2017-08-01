## RxJS Devtools

This is a chrome extension that can be used to visualize RxJS streams in realtime. 

**Disclaimer:** This project started out as a POC to see if it was possible to visualize RxJS streams. It was later redefined as a chrome extension. This project is still a WIP. I encourage you to use it but remember, at this moment in time it is still in an early alpha phase and might not always work properly. I haven't properly tested all the operators, check the table below to see which ones should be working as of the current version. Feel free to create github issues when you discover problems, I will try to tackle them asap. 
 
### Installation

#### In your project

Install the following dependency in your project using yarn:

```yarn add rx-devtools```

or npm:

```npm i -S rx-devtools```

Initialize the package by calling the `setupRxDevtools` function:

```
import { setupRxDevtools } from 'rx-devtools/rx-devtools';
setupRxDevtools();
```

** Note: this should only be active in a development environment. Try to avoid having this code in your production build.**

#### Chrome extension



### How to use

The extension can be used to visualize streams in your application using marble diagrams. To make the extension work, open your developer tools and open the 'RxDevtools' tab. The tab has to be open before the extension will work (I'm trying to find a way around this). 

The extension will capture the emissions of observables for a certain timeframe. The timeframe at this moment in time is not configurable and is set to 15s (this will be fixed asap, see todo's at the bottom). The extension will start counting as soon as the application starts and will show the marbles onto the marble diagrams with a timeframe of 15s in mind. If a value is emitted after 5s of this 15s timeframe, it will be visualized at 33% of the marble diagrams length. Every value arriving after this 15s timeframe will be visualised at the end (again, this will be fixed asap). 


You are all set to go.

### Supported and tested operators*

| Operators        | Tested           | Supported since |
| ------------- |:-------------:| -----:|
| Map      |yes|0.0.1-alpha.29|
| Filter      | yes|  0.0.1-alpha.29 |
| Take | yes     |    0.0.1-alpha.29 |
| Skip | yes     |    0.0.1-alpha.29 |
| MergeMap | yes     |    0.0.1-alpha.29 |
| Do | yes     |    0.0.1-alpha.29 |
| StartWith | yes     |    0.0.1-alpha.29 |
| CombineLatest | yes     |    0.0.1-alpha.29 |
| Zip | yes     |    0.0.1-alpha.29 |
| Concat | yes     |    0.0.1-alpha.29 |

* This is a non-exhaustive list. The extension will definitely support more operators as of today but they aren't all properly tested. The ones above have been tested and should be working.


#### TODO

- [ ] Make the recording timeframe resettable
- [ ] Visualize different subscriptions on the same stream properly (currently they are visualized on the same marble diagram)

(If you have any addition you want in this library, let me know through github issues).
