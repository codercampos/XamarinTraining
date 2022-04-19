## FlyoutPage
1. Create a new Mobile app using Xamarin Forms project.
2. Let's change our MainPage to use a FlyoutPage instead of ContentPage, so It look like this:
``` xml
<?xml version="1.0" encoding="utf-8"?>
<FlyoutPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
             x:Class="MasterPageSample.MainPage">
    <FlyoutPage.Flyout>
    <!-- Here will be our Flyout part or most commonly named as "menu" -->
    </FlyoutPage.Flyout>
    <FlyoutPage.Detail>
    <!-- Here will be our Detail page -->
    </FlyoutPage.Detail>
</FlyoutPage>
```

3. Flyout is a container that c