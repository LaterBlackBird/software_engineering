the entire HTML is generated at build time and does not change until the next build.  This makes caching the site on a CDN or Edge Network possible.

### Most Suitable for: 
pages that don't change often and display the same data no matter who requests it.

<img src='https://res.cloudinary.com/ddxwdqwkr/image/upload/v1658990025/patterns.dev/img1.png' />
<img src='https://res.cloudinary.com/ddxwdqwkr/image/upload/v1658990025/patterns.dev/8.png' />

### Static rendering with client-side `fetch`
still uses the basis of static rendering to produce a skeleton UI, then after the page loads, we fetch data.  Shows dynamic data on each request.  Another disadvantage is that this approach could result in **higher server costs** since we call the API route once per page request.
<img src="https://res.cloudinary.com/ddxwdqwkr/image/upload/v1658990025/patterns.dev/13.png">

### Static with `getStaticProps`
if data is available at build time and is not needed to updated on each request, use the `getStaticProps` method.  Can result in long build times as API's are called repeatedly on larger websites.  If you're using an external API, you might hit the request limit or run a **large usage bill**.
<img src='https://res.cloudinary.com/ddxwdqwkr/image/upload/v1658990025/patterns.dev/17.png'/>

### Incremental Static Regeneration (ISR)
a hybrid of static and client-side fetch - pre-render only certain static pages and render dynamic pages on-demand.  This results in shorter build times and allows automatic invalidation of the cache and regeneration of the page after a specific interval.  With Incremental Static Regeneration, we can show dynamic content by automatically revalidating the page every few seconds.  Our content likely doesn't update as often as the interval we have defined. This would result in unnecessary page regeneration and invalidation of the cache. Each time this happens, we invoke our serverless functions, which could result in higher server costs.

<img src='https://res.cloudinary.com/ddxwdqwkr/image/upload/v1658990025/patterns.dev/23.png'/>


### On-demand Incremental Static Regeneration
allows us to use ISR, but the regeneration occurs on certain events rather than at fixed intervals.  On-demand ISR regenerates and redistributes the page across the edge network so that users worldwide will automatically see the most recent version of the page from the edge cache without seeing stale content. We also avoid unnecessary regenerations and serverless function calls, reducing operational costs compared to regular ISR.

<img src='https://res.cloudinary.com/ddxwdqwkr/image/upload/v1658990025/patterns.dev/26.png'/>


