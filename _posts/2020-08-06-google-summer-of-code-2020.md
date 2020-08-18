---
layout: post
title: "Google Summer of Code with The Mifos Initiative"
date: 2020-08-06 20:03:36
categories: gsoc
---

My experience working with The Mifos Initiative for Google Summer of Code 2020  

<img src="https://raw.githubusercontent.com/ashwinkey04/ashwinkey04.github.io/master/images/post_gsoc/head.png" width = 600>

## Prelude
Google Summer of Code, also known as GSoC, is an initiative by Google for encouraging student developers to contribute to Open Source Software. For its 2020 edition, I proposed to work with [The Mifos Initiative](https://www.mifos.org/) which is a fin-tech organization, aimed at providing technology-enabled financial inclusion to those who are underbanked all around the world. 

I spent the summer working with [mifos-mobile](https://github.com/openMF/mifos-mobile) - a customer facing mobile application built on top of MifosX which enables the customer to access their bank account using their smartphone. The app was built using Java. I converted the app to Kotlin, so as to enjoy the benefits that Kotlin offers over Java, and enable cross-platform development in the future using Kotlin multi-platform.


## Why Kotlin? 
Kotlin is a powerful language and using Kotlin for Mifos Mobile has the same reasons as to why nearly all android developers prefer Kotlin over Java. 
* **Modern**: Kotlin is a new language that has adapted and corrected mistakes over the time. It is also a very concise language and that would be very obvious after you start using it. A quick example for that is - No more semi-colons! 
* **Interoperable**: Kotlin generates the same bytecode as what Java does. So Kotlin can seamlessly call Java code and vice-versa. So developing using Kotlin on top of a Java project is an easy thing.
* **Adios Null Pointer Exceptions**: 
Null type is integrated into the language's type system itself. So it is not necessary to keep wrapping codes with null checks around it to avoid NPE, the *billion dollar mistake*
* **Multi platform**: Kotlin is not limited just for android development. Kotlin Native opens possibilities for Kotlin to support almost any platform. This is also among the main reasons for Mifos Mobile to adopt Kotlin, so that the app will soon support iOS development in the same codebase. 


## Work done
#### [PR #1516](https://github.com/openMF/mifos-mobile/pull/1516):
- Depended on Kotlin `kapt` instead of `annotationProcessor` and implemented `annotationLibrary` from android Jetpack library to support annotations post converting the app to Kotlin. 
- Converted authentication method to support the new authentication method used by the fineract backend where the user's credentials are passed in the API request's JSON body. Rewrote tests to support the new authentication method too.
- Converted Login activity to Kotlin

#### [PR #1526](https://github.com/openMF/mifos-mobile/pull/1526):
 - Converted the following classes which were previously in Java to Kotlin, which translates to converting the app completely to Kotlin. 
1.  Passcode activity
2.  Constants
3.  Convert Registration activity
4.  Home activity and fragments
5.  Base activity and fragments
6.  API related classes
7.  All View classes
8.  All classes under  `/main/../ui`  (Activities, Adapters, Enums, Views, Widgets, Fragments)
9.  All Adapter classes
10.  All Presenter classes
11.  All JUnit tests
12.  All activity classes
13.  All model classes
14.  All Injection classes
15.  `MifosSelfService` class
16.  `commonTest` and `androidTest` classes

#### [API Matrix](https://docs.google.com/spreadsheets/d/1gR84jZzLF-mM0iRw5JyeMAsHMK6RQPK0vyDmNAY9VhE/edit?usp=sharing):
<img src="https://raw.githubusercontent.com/ashwinkey04/ashwinkey04.github.io/master/images/post_gsoc/api_matrix.png" width = 1200>

- Compiled and organized all the APIs consumed by Mifos mobile and organized in a google sheet for future reference


## Scope of Work
#### ButterKnife to ViewBinding
The Jetpack library offers a robust alternative to ButterKnife, which is View Binding. There are some advantages like
- No more `@BindView` annotations, drastically reduces boilerplate code.
- Type safety and Null Safety inbuilt
- No `@OnClick` annotations required

#### Convert `ProgressDialog` to `progressBar`
`ProgressDialog` was depreceated in Java and all instances of the same in the app can be converted to `progressBar`

#### Missed out nullable variables and in line initializations
There might be a few variables which still remain non-nullable post conversion from Java and also some class properties which doesn't enjoy Kotlin's inline initialization and uses an `init{}` block instead. Those instances can be converted to fully support Kotlin's features.

## Wrap up
Big thanks to my primary mentor [Saksham Handu](https://github.com/miPlodder), for constantly guiding me throughout the working period and helping me amidst his busy schedule and org admin & CEO of Mifos [Ed Cable](https://github.com/edcable) for helping the class of interns to communicate with the organization and getting our blockers resolved. Thanks to all the fellow developers who helped each other whenever needed. 
