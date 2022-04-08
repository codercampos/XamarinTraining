## Carousel Page
1. Create a new Mobile app using Xamarin Forms project.
2. Let's change our MainPage to use a CarouselPage instead of ContentPage, so It look like this:
``` xml
<?xml version="1.0" encoding="utf-8"?>
<CarouselPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:local="clr-namespace:CarouselPageSample" 
             x:Class="CarouselPageSample.MainPage">
</CarouselPage>
```

Note: Since We have change the MainPage xaml file to use CarouselPage, You need to change the base class of MainPage.xaml.cs

``` csharp
using Xamarin.Forms;

namespace CarouselPageSample
{
    public partial class MainPage : ContentPage
    {
        public MainPage()
        {
            InitializeComponent();
        }
    }
}
```
To
``` csharp
using Xamarin.Forms;

namespace CarouselPageSample
{
    public partial class MainPage : CarouselPage
    {
        public MainPage()
        {
            InitializeComponent();
        }
    }
}
```

3. CarouselPage is a container of pages, So let's add 3 pages to MainPage.xaml:

``` xml
<?xml version="1.0" encoding="utf-8"?>
<CarouselPage xmlns="http://xamarin.com/schemas/2014/forms" 
             xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml" 
             xmlns:local="clr-namespace:CarouselPageSample" 
             x:Class="CarouselPageSample.MainPage">
             
    <ContentPage BackgroundColor="Black">
        <!-- First page -->
    </ContentPage>
       
    <ContentPage BackgroundColor="Black">
        <!-- Second page -->
    </ContentPage>

    <ContentPage BackgroundColor="Black">
        <!-- Third page -->
    </ContentPage>
</CarouselPage>
```

4. Let's add content to our pages. For each page We will add 1 Image, 2 labels and a Button. Your XAML code should look like this:

``` xml
<?xml version="1.0" encoding="utf-8"?>
<CarouselPage xmlns="http://xamarin.com/schemas/2014/forms"
              xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
              x:Class="CarouselPageSample.MainPage">
    <ContentPage BackgroundColor="Black">
        <StackLayout Orientation="Vertical" HorizontalOptions="Center" VerticalOptions="Center" Padding="25">
            <Image Source="Slide1" />
            <Label Text="Learning Together" />
            <Label Text="We help your children to learn in a funny way" Margin="25"
                   Style="{StaticResource DescriptionWTStyle}" />
            <Button Text="GET STARTED" />
        </StackLayout>
    </ContentPage>

    <ContentPage BackgroundColor="Black">
        <StackLayout Orientation="Vertical" HorizontalOptions="Center" VerticalOptions="Center" Padding="25">
            <Image Source="Slide2" />
            <Label Text="IN A FUNNY WAY!" />
            <Label Text="Come to learn with us" Margin="25" />
            <Button Text="GET STARTED" />
        </StackLayout>
    </ContentPage>

    <ContentPage BackgroundColor="Black">
        <StackLayout Orientation="Vertical" HorizontalOptions="Center" VerticalOptions="Center" Padding="25">
            <Image Source="Slide3" />
            <Label Text="GRADUATION EVENTS" />
            <Label Text="Your children wil be abe to graduate" Margin="25"
                   Style="{StaticResource DescriptionWTStyle}" />
            <Button Text="GET STARTED" />
        </StackLayout>
    </ContentPage>
</CarouselPage>
```

### Bonus: Let's add styles to our CarouselPage project
Styles are resources to customize and standarise our app, this is a good way to set up our brand in our project. More info about styles, click [here](https://docs.microsoft.com/en-us/xamarin/get-started/quickstarts/styling?pivots=windows).

1. Open App.xaml and add the following code inside the Application attribute:
``` xml
<Application.Resources>
    <Style x:Key="HeaderWtStyle" TargetType="Label">
        <Setter Property="FontSize" Value="20" />
        <Setter Property="TextColor" Value="White" />
        <Setter Property="HorizontalOptions" Value="CenterAndExpand" />
        <Setter Property="FontAttributes" Value="Bold" />
    </Style>

    <Style x:Key="ImageWtStyle" TargetType="Image">
        <Setter Property="VerticalOptions" Value="CenterAndExpand" />
        <Setter Property="HeightRequest" Value="150" />
        <Setter Property="WidthRequest" Value="60" />
        <Setter Property="Margin" Value="0,40" />
    </Style>

    <Style x:Key="DescriptionWtStyle" TargetType="Label">
        <Setter Property="HorizontalTextAlignment" Value="Center" />
        <Setter Property="TextColor" Value="White" />
        <Setter Property="FontSize" Value="15" />
    </Style>

    <Style x:Key="BtnGetStartedStyle" TargetType="Button">
        <Setter Property="BackgroundColor" Value="#52BEFF" />
        <Setter Property="TextColor" Value="White" />
        <Setter Property="VerticalOptions" Value="End" />
        <Setter Property="HorizontalOptions" Value="Center" />
        <Setter Property="WidthRequest" Value="255" />
    </Style>
</Application.Resources>
```
2. Add each style to each component within our MainPage:
   - HeaderWtStyle will be for our header label
   - ImageWtStyle will be for our images
   - DescriptionWtStyle will be for each description
   - BtnGetStartedStyle will be for each button

Our final code will look like this:
 ``` xml
 <?xml version="1.0" encoding="utf-8"?>
<CarouselPage xmlns="http://xamarin.com/schemas/2014/forms"
              xmlns:x="http://schemas.microsoft.com/winfx/2009/xaml"
              x:Class="CarouselPageSample.MainPage">
    <ContentPage BackgroundColor="Black">
        <StackLayout Orientation="Vertical" HorizontalOptions="Center" VerticalOptions="Center" Padding="25">
            <Image Source="Slide1" Style="{StaticResource ImageWtStyle}" />
            <Label Text="Learning Together" Style="{StaticResource HeaderWtStyle}" />
            <Label Text="We help your children to learn in a funny way" Margin="25"
                   Style="{StaticResource DescriptionWtStyle}" />
            <Button Text="GET STARTED" Style="{StaticResource BtnGetStartedStyle}" />
        </StackLayout>
    </ContentPage>

    <ContentPage BackgroundColor="Black">
        <StackLayout Orientation="Vertical" HorizontalOptions="Center" VerticalOptions="Center" Padding="25">
            <Image Source="Slide2" Style="{StaticResource ImageWtStyle}" />
            <Label Text="IN A FUNNY WAY!" Style="{StaticResource HeaderWtStyle}" />
            <Label Text="Come to learn with us" Margin="25" Style="{StaticResource DescriptionWtStyle}" />
            <Button Text="GET STARTED" Style="{StaticResource BtnGetStartedStyle}" />
        </StackLayout>
    </ContentPage>

    <ContentPage BackgroundColor="Black">
        <StackLayout Orientation="Vertical" HorizontalOptions="Center" VerticalOptions="Center" Padding="25">
            <Image Source="Slide3" Style="{StaticResource ImageWtStyle}" />
            <Label Text="GRADUATION EVENTS" Style="{StaticResource HeaderWtStyle}" />
            <Label Text="Your children wil be abe to graduate" Margin="25"
                   Style="{StaticResource DescriptionWtStyle}" />
            <Button Text="GET STARTED" Style="{StaticResource BtnGetStartedStyle}" />
        </StackLayout>
    </ContentPage>
</CarouselPage>
 ```

 The app will look like this (don't forget to swipe left and right):

 | iOS | Android |
 | --- | --- |
 | <img src="../Screenshots/screen04.png" height="300" /> | <img src="../Screenshots/screen03.png" height="300" /> |