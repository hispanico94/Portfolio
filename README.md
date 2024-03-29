# Paolo Rocca
![](Images/github_profile_pic.png)
### iOS Developer

[![](https://img.shields.io/badge/GitHub-hispanico94-lightgrey)](https://github.com/hispanico94) [![](https://img.shields.io/badge/LinkedIn-Paolo%20Rocca-blue)](https://www.linkedin.com/in/paolo-rocca-ab4617171/) [![](https://img.shields.io/badge/Twitter-hispanico94-9cf)](https://twitter.com/hispanico94)

# Current Position

iOS Developer @ [Prima Assicurazioni S.p.A.](https://www.prima.it/)

# Personal Projects

## Guzzi Tracker

![](Images/gt1.png) ![](Images/gt2.png) ![](Images/gt3.png) ![](Images/gt4.png)

Year: 2017 - 2019

Tecnologies: `Swift`, `UIKit`, `Carthage`, `Kingfisher`, `MVC`, `Codable`, `Measurement`, `Auto Layout`, `Localization`

Guzzi Tracker was my first app developed from scratch. It's a reference guide of all the technical specs of (almost) all the motorcycles manufactured by Moto Guzzi since 1921. I developed the app between 2017 and 2018 and it was available on the App Store from september 2018 to december 2019.

The app it's entirely written in Swift (updated to version 5) using MVC architecture. There is only one external library, [Kingfisher](https://github.com/onevcat/Kingfisher), managed using Carthage. Few months ago I updated the app to support iOS 13 with Dark Mode, `.pageSheet` modal presentation style and automatic collection diffing. It also supports Master-Detail interface and readable content width. The app is localized in italian and english. I also experimented with a bit of functional programming while designing the filtering and sorting of the motorcycle list. 

I'm very proud of Guzzi Tracker, being my first real app, developed with no working experience and published on the App Store.

The project is available on the [Guzzi Tracker repo](https://github.com/hispanico94/Guzzi-Tracker). A detailed README of the project is also available.

## PassIT

![](Images/passit1.png) ![](Images/passit2.png) ![](Images/passit3.png) ![](Images/passit4.png)

Year: 2018 - 2019

Tecnologies: `Swift`, `UIKit`, `Carthage`, `MVVM`, `RxSwift/RxCocoa`, `RxDataSources`, `CoreLocation`, `MapKit`, `Auto Layout`

PassIT is a toy project I developed between fall 2018 and winter 2019 while I was studying reactive programming using RxSwift and MVVM architecture. The app lists and shows on a map 438 road passes and road to mountain peaks in Italy. I took inspiration from my passion about motorcycles, just like Guzzi Tracker! For every pass o road peak some informations are reported, including name, address, elevation and distance and travel time from the user position calculated using `MKDirections`.

The app it's entirely written in Swift (updated to version 5) using a mix of MVC and MVVM architecture. It uses RxSwift and RxCocoa for reactive bindings, and [RxDataSources](https://github.com/RxSwiftCommunity/RxDataSources) for reactive data sources for table views. I created custom reactive extensions for MKDirections, MKMapView and CLLocationManager for simplifying the bindings. Like in Guzzi Tracker, here I also experimented a bit with functional programming, applying the concepts of the functional getters and setters exposed in the episodes [#6](https://www.pointfree.co/episodes/ep6-functional-setters), [#7](https://www.pointfree.co/episodes/ep7-setters-and-key-paths) and [#8](https://www.pointfree.co/episodes/ep8-getters-and-key-paths) of the [Point Free](https://www.pointfree.co) video series.

I really enjoyed studying reactive programming, RxSwift and MVVM and playing with them by creating this toy project. Now MVVM using RxSwift is my default way to go when working on real projects at my current company.

This project is available on the [PassIT repo](https://github.com/hispanico94/PassIT).

## Air Monitor

![](Images/am1.png) ![](Images/am2.png) ![](Images/am3.png) ![](Images/am4.png)

Year: 2020

Tecnologies: `Swift`, `SwiftUI`, `UIKit`, `Combine`, `URLSession`, `The Composable Architecture`

Air Monitor is my latest toy project. I started developing this app for studying SwiftUI and Combine. The app shows the air quality data collected in many locations around the world by the [OpenAQ Organization](https://openaq.org/) and calculates the air quality index based on the [EAQI specifications](https://airindex.eea.europa.eu/). The app shows the most recent measurements of pollutants like **PM10**, **PM2,5**, **SO2**, **NO2** and **O3** and also shows the trends of the last 30 days of the same pollutants. The actual pollutants and trends showed depends on the data available on the OpenAQ database. If no data from the last 30 days is available for the selected location an alert will be presented to the user. The colors showed represent the EAQI index level for every measuerment and pollutant.

The app fetches the data from the [OpenAQ public APIs](https://docs.openaq.org) using `URLSession.DataTaskPublisher`. Then the data is processed for calculating the latest EAQI index based on the available data and it's shown in SwiftUI's `View`s. The `UIActivityIndicator` (and previously the `UISearchBar` also) is integrated in all views thanks to the `UIViewRepresentable` protocol for wrapping UIKit elements into SwiftUI views. The architecture used is [The Composable Architecture](https://github.com/pointfreeco/swift-composable-architecture) by Brandon Williams and Stephen Celis at [Point-Free](https://www.pointfree.co). This is a very opinionated but great architecture with composition, modularity and testing in mind and it was specifically made for working with SwiftUI (although it's perfectly usable also on UIKit projects). It was very fun replacing the previous architecture I used for developing the app (MVVM) with TCA, I suggest everyone to give it a try!

This project is available on the [Air Monitor repo](https://github.com/hispanico94/Air-Monitor).

## SimplyAuth (WIP)

![](Images/sa1.jpeg) ![](Images/sa2.jpeg) ![](Images/sa3.jpeg) ![](Images/sa4.jpeg)

Year: 2020 - 2021

Tecnologies: `Swift`, `SwiftUI`, `UIKit`, `CryptoKit`, `Security (Keychain)`, `AVFoundation`, `The Composable Architecture`

I started developing SimplyAuth for keeping practicing with SwiftUI and looking into `CryptoKit`, the cryptography framework release by Apple with iOS 13. This app handles the storage and generation of time-based and counter-based **One Time Password**s (**TOTP** and **HOTP**), like the [Google Authenticator app](https://apps.apple.com/it/app/google-authenticator/id388497605). 

With CryptoKit developing a library for handling HOTP and TOTP is fairly easy. I started by studying the IETF's [RFC 4226](https://tools.ietf.org/html/rfc4226) and [RFC 6238](https://tools.ietf.org/html/rfc6238) documents. I later then defined what a [Password](https://github.com/hispanico94/SimplyAuth/blob/master/SimplyAuth/SimplyAuth/Models/Password.swift) is and then I defined a [couple of functions](https://github.com/hispanico94/SimplyAuth/blob/master/SimplyAuth/SimplyAuth/OTP/OTPExtractor.swift) that can extract a TOTP or HOTP based on the password and the current timestamp or counter associated with the password.
The passwords are safely stored in the Keychain via the `Security` framework, no third party library was used. A [single entity](https://github.com/hispanico94/SimplyAuth/blob/master/SimplyAuth/SimplyAuth/Keychain/Keychain.swift) manages the saving, retrieving and deleting of passwords, and the passwords are stored as JSON data.

The OTP can be added manually, by entering the required data (including advanced options like the algorithm, digits and start counter for HOTP or time interval for TOTP, although standard defaults are provided), or by scanning a QR code. The scanning is provided by AVFoundation and bridged to SwiftUI thanks to the `UIViewControllerRepresentable` protocol, no external libraries are used. The parsing of the underlying URL is done according to Google's [Key URI Format](https://github.com/google/google-authenticator/wiki/Key-Uri-Format) specifications.
The *secret*s for the OTPs are *Base32* encoded, for this reason the third party dependency [Bases](https://github.com/mattrubin/Bases) is inclued in the project via Swift Package Manager. This library simplify the decoding of the Base32 string for the secret. If the secret is provided by manually entering the data, this must also be a Base32 encoded string. 
Users can reorder OTPs on the home view, they can also edit or delete OTPs by long-tapping on a OTP thanks to the context menu. By single tapping on a OTP the user can copy the current OTP on the clipboard. On certain interactions an haptic feedback is provided thanks to UIKit's `UIFeedbackGenerator` class.

Like Air Monitor, the architecture used for SimplyAuth is [The Composable Architecture](https://github.com/pointfreeco/swift-composable-architecture) by Brandon Williams and Stephen Celis at [Point-Free](https://www.pointfree.co). This is the other third party dependency used in the project and it's also added via Swift Package Manager.

I'm still working on this project, but if you want to check out the source code it's available on the [SimplyAuth repo](https://github.com/hispanico94/SimplyAuth).
