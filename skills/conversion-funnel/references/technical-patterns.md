# Technical Implementation Patterns

## Landing Page HTML Skeleton

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>[Headline] | [Brand]</title>

    <!-- GA4 with conversion tracking -->
    <script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXX"></script>
    <script>
      window.dataLayer = window.dataLayer || [];
      function gtag(){dataLayer.push(arguments);}
      gtag('js', new Date());
      gtag('config', 'G-XXXXXXX');
    </script>

    <!-- UTM persistence -->
    <script>
    (function() {
      var params = new URLSearchParams(window.location.search);
      ['utm_source','utm_medium','utm_campaign','utm_term','utm_content'].forEach(function(p) {
        var v = params.get(p);
        if (v) sessionStorage.setItem(p, v);
      });
    })();
    </script>
</head>
<body>
    <!-- ABOVE THE FOLD -->
    <section id="hero">
        <p class="pre-headline">For [Dream Buyer] who want [Result]</p>
        <h1>[Big Promise] in [Timeframe] — Without [Fear/Pain]</h1>
        <p class="sub-headline">[Specificity: numbers, method name, proof]</p>
        <a href="#opt-in" class="cta-button">[Action-Oriented CTA]</a>
        <img src="hero-mockup.png" alt="[Lead Magnet Name]">
    </section>

    <!-- SOCIAL PROOF BAR -->
    <section id="proof">
        <p>Trusted by X,XXX [role]s at:</p>
        <div class="logo-bar"><!-- Company logos --></div>
    </section>

    <!-- PROBLEM AGITATION -->
    <section id="problem">
        <h2>You're [pain point], and it's costing you [measurable loss]</h2>
    </section>

    <!-- SOLUTION + EPIPHANY BRIDGE -->
    <section id="solution">
        <h2>There's a better way</h2>
        <!-- Backstory → aha moment → method → result -->
    </section>

    <!-- OFFER STACK -->
    <section id="offer">
        <h2>Here's everything you get</h2>
        <!-- Stack slide: item + value, repeat -->
    </section>

    <!-- RISK REVERSAL -->
    <section id="guarantee">
        <h2>[X]-Day [Result] Guarantee</h2>
        <p>Try it for [X] days. If you don't [specific result],
           we'll refund every penny. No questions.</p>
    </section>

    <!-- OPT-IN FORM -->
    <section id="opt-in">
        <form id="funnel-form">
            <input type="text" name="name" placeholder="First Name" required>
            <input type="email" name="email" placeholder="Email Address" required>
            <input type="hidden" name="utm_source" id="utm_source">
            <input type="hidden" name="utm_medium" id="utm_medium">
            <input type="hidden" name="utm_campaign" id="utm_campaign">
            <button type="submit">[CTA: "Get Instant Access"]</button>
        </form>
    </section>

    <!-- FAQ -->
    <section id="faq">
        <!-- 5-7 objections disguised as questions -->
    </section>

    <script>
    // Populate UTM hidden fields
    document.addEventListener('DOMContentLoaded', function() {
      ['utm_source','utm_medium','utm_campaign'].forEach(function(p) {
        var el = document.getElementById(p);
        if (el) el.value = sessionStorage.getItem(p) || '';
      });
    });

    // Form submission with GA4
    document.getElementById('funnel-form').addEventListener('submit', function(e) {
      e.preventDefault();
      gtag('event', 'generate_lead', {
        event_category: 'funnel',
        event_label: '[Lead Magnet Name]'
      });
      // Submit to your API / email provider
    });
    </script>
</body>
</html>
```

## Checkout Flow with Upsell

```
Opt-In Page → Thank-You + Tripwire → Checkout → OTO Upsell → Confirmation
     |                |                  |            |              |
  GA4: lead      GA4: view_item    GA4: purchase  GA4: purchase   Email drip
                                   (tripwire)     (upsell)        begins
```

## GA4 Conversion Events

```javascript
// Lead captured (opt-in form submitted)
gtag('event', 'generate_lead', {
  event_category: 'funnel',
  event_label: 'lead_magnet_name'
});

// Checkout started
gtag('event', 'begin_checkout', {
  event_category: 'ecommerce',
  currency: 'USD',
  value: 47.00
});

// Purchase completed
gtag('event', 'purchase', {
  event_category: 'ecommerce',
  transaction_id: 'T-12345',
  currency: 'USD',
  value: 47.00,
  items: [{ item_name: 'Product Name', price: 47.00 }]
});

// Upsell accepted
gtag('event', 'purchase', {
  event_category: 'ecommerce',
  transaction_id: 'T-12345-OTO',
  currency: 'USD',
  value: 197.00,
  items: [{ item_name: 'Upsell Product', price: 197.00 }]
});
```

## UTM Parameter Tracking

Preserve UTM parameters across the entire funnel:

```javascript
// On every page — save UTMs to sessionStorage
(function() {
  var params = new URLSearchParams(window.location.search);
  ['utm_source','utm_medium','utm_campaign','utm_term','utm_content'].forEach(function(p) {
    var v = params.get(p);
    if (v) sessionStorage.setItem(p, v);
  });
})();

// When submitting forms or creating checkout links — append UTMs
function getUtmParams() {
  var utms = {};
  ['utm_source','utm_medium','utm_campaign','utm_term','utm_content'].forEach(function(p) {
    var v = sessionStorage.getItem(p);
    if (v) utms[p] = v;
  });
  return utms;
}

// Append to API calls
fetch('/api/leads', {
  method: 'POST',
  body: JSON.stringify({ ...formData, ...getUtmParams() })
});
```

## Key Metrics Dashboard

```
TRAFFIC
├── Visitors/day by source
├── Cost per click (CPC) by channel
└── Traffic temperature (cold/warm/hot %)

CONVERSION
├── Opt-in rate (target: 25-45%)
├── Tripwire conversion (target: 5-15% of leads)
├── Core offer conversion (target: 2-5% of leads)
├── Upsell take rate (target: 15-30% of buyers)
└── Cart abandonment rate

REVENUE
├── Earnings per lead (EPL) = total revenue / total leads
├── Customer acquisition cost (CAC)
├── Average order value (AOV)
├── Customer lifetime value (LTV)
└── LTV:CAC ratio (target: 3:1 minimum)

EMAIL
├── Open rate (target: 25-40%)
├── Click rate (target: 3-7%)
├── Unsubscribe rate (warning if > 1%)
└── Revenue per email sent
```
