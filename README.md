# Trestle [![Android Arsenal](https://img.shields.io/badge/Android%20Arsenal-Trestle-brightgreen.svg?style=flat)](http://android-arsenal.com/details/1/1916)
A framework used to bridge one or more spans for use with a TextView

Supports the following spans :

`ForegroundColorSpan`
`BackgroundColorSpan`
`CustomTypefaceSpan`
`RelativeSizeSpan`
`AbsoluteSizeSpan`
`URLSpan`
`UnderlineSpan`
`StrikethroughSpan`
`QuoteSpan`
`SubscriptSpan`
`SuperscriptSpan`
`ClickableSpan`
`ScaleXSpan`

Also supports one or more spans, spanning the length of a regex match

![Trestle](https://raw.githubusercontent.com/lawloretienne/Trestle/master/images/Trestle_Screenshot2.png)

## Setup

#### Gradle

`compile 'com.github.lawloretienne:trestle:0.0.2'`

#### Maven
```
<dependency>
    <groupId>com.github.lawloretienne</groupId>
    <artifactId>trestle</artifactId>
    <version>0.0.2</version>
</dependency>
```

## Sample Usage

```java
// Setup single span
TextView tv1 = (TextView) view.findViewById(R.id.tv1);

CharSequence formattedText1 = Trestle.getFormattedText(
        new Span.Builder("ForegroundSpan, BackgroundSpan, and CustomTypefaceSpan")
                .foregroundColor(getResources().getColor(R.color.purple_100)) // Pass resolved color instead of resource id
                .backgroundColor(getResources().getColor(R.color.green_500)) // Pass resolved color instead of resource id
                .typeface(mItalicFont)
                .build());

tv1.setText(formattedText1);

// Setup multiple spans
TextView tv2 = (TextView) view.findViewById(R.id.tv2);

List<Span> spans1 = new ArrayList<>();
spans1.add(new Span.Builder("ForegroundSpan")
        .foregroundColor(getResources().getColor(R.color.red_500)) // Pass resolved color instead of resource id
        .build());
spans1.add(new Span.Builder("BackgroundSpan")
        .backgroundColor(getResources().getColor(R.color.yellow_500)) // Pass resolved color instead of resource id
        .build());
spans1.add(new Span.Builder("ForegroundSpan and BackgroundSpan")
        .foregroundColor(getResources().getColor(R.color.brown_500)) // Pass resolved color instead of resource id
        .backgroundColor(getResources().getColor(R.color.blue_300)) // Pass resolved color instead of resource id
        .build());
spans1.add(new Span.Builder("ForegroundSpan, BackgroundSpan, and CustomTypefaceSpan")
        .foregroundColor(getResources().getColor(R.color.green_700)) // Pass resolved color instead of resource id
        .backgroundColor(getResources().getColor(R.color.indigo_200)) // Pass resolved color instead of resource id
        .typeface(mRegularFont)
        .build());

CharSequence formattedText2 = Trestle.getFormattedText(spans1);

tv2.setText(formattedText2);
```

## License

```
Copyright 2015 Etienne Lawlor

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
