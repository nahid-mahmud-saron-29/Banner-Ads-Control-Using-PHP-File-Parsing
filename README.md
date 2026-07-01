# Android Ads Control using Static Variable

এই প্রজেক্টে দেখানো হয়েছে কীভাবে একটি `public static boolean` ভ্যারিয়েবল ব্যবহার করে সার্ভারের রেসপন্স অনুযায়ী পুরো অ্যাপের বিজ্ঞাপন (Ads) নিয়ন্ত্রণ করা যায়।

## 📌 এটি কীভাবে কাজ করে?
1. **MainActivity**-তে Volley লাইব্রেরি ব্যবহার করে সার্ভার থেকে ডেটা আনা হয়।
2. রেসপন্স "SHOW" হলে `public static boolean SHOW_ADS = true;` সেট করা হয়।
3. **MainActivity2** বা অন্য যেকোনো অ্যাক্টিভিটি থেকে সরাসরি `MainActivity.SHOW_ADS` চেক করে বিজ্ঞাপন দেখানো বা হাইড করা হয়।

## 🛠️ কোড ইমপ্লিমেন্টেশন (Code Implementation)

### MainActivity.java
```java
public class MainActivity extends AppCompatActivity {
    public static boolean SHOW_ADS = false; // গ্লোবাল স্ট্যাটিক ভ্যারিয়েবল

    // Volley Response এর ভেতরে:
    if (response.contains("SHOW")){
        SHOW_ADS = true;
    }
}












if (MainActivity.SHOW_ADS){
    // বিজ্ঞাপন লোড করার কোড
    adView.setVisibility(View.VISIBLE);
} else {
    adView.setVisibility(View.GONE);
}
