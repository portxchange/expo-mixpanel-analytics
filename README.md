# `@portxchange/expo-mixpanel-analytics`

Mixpanel integration for use with React Native apps built on Expo. This package is based on Mollie's fork of `@benawad/expo-mixpanel-analytics`, but does not store the device name in Mixpanel for privacy reasons, and also connects to the EU endpoint of Mixpanel for GDPR compliance.

## Installation

```
yarn add @portxchange/expo-mixpanel-analytics
```

## Import

Your React Native app's screen resolution, app name, app ID, app version, device information and multiple other parameters will be automatically resolved and sent with each event.

```
import ExpoMixpanelAnalytics from '@portxchange/expo-mixpanel-analytics';
```

## Usage

```
const analytics = new ExpoMixpanelAnalytics("5224da5bbbed3fdeaad0911820f1bf2x");

analytics.identify("13793");

analytics.register({ email: "bob@bob.com" }); // super props sent on every request and persisted in AsyncStorage

analytics.track("Signed Up", { "Referred By": "Friend" });

analytics.people_set({ "$first_name": "Joe", "$last_name": "Doe", "$email": "joe.doe@example.com", "$created": "2013-04-01T13:20:00", "$phone": "4805551212", "Address": "1313 Mockingbird Lane", "Birthday": "1948-01-01" });

analytics.people_set_once({ "First login date": "2013-04-01T13:20:00" });

analytics.people_unset([ "Days Overdue" ]);

analytics.people_increment({ "Coins Gathered": 12 });

analytics.people_append({ "Power Ups": "Bubble Lead" });

analytics.people_union({ "Items purchased": ["socks", "shirts"] });

analytics.people_delete_user();

analytics.reset();
```

## References

`https://mixpanel.com/help/reference/http`
