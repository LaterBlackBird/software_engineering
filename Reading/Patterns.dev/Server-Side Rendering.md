With server-side rendering, we generate the HTML for every request. This approach is most suitable for pages containing highly personalized data.  It's also suitable for pages that should be render-blocking, perhaps based on authentication state.

<img src='https://res.cloudinary.com/ddxwdqwkr/image/upload/v1658990025/patterns.dev/28.png'/>

<img src='https://res.cloudinary.com/ddxwdqwkr/image/upload/v1658990025/patterns.dev/32.png'/>

To optimze SSR performance we can:
1) Avoid long `getServerSideProps` execution
2) Deploy serverless functions in a region close to your databse
3) Add `Cache-Control` headers if we can't use ISR
4) Upgrade server hardware

### Edge SSR
distributes the build across multiple regions, making the cold-boot time for serverless functions near-zero.

### Edge Streaming SSR
the advantages of edge streaming SSR but streaming pieces of the UI in intervals, hydrating those components as they are available.  The combination of **Edge SSR with React Server Components** can allow us to have a beautiful **hybrid between static and server rendering**

