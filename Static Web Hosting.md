# Hosting a Multi-Page Static Website using AWS S3

## Problem

I wanted to host a simple multi-page website without running a server.

## Architecture

Browser → AWS S3 → Static HTML Files

## Implementation

* Created an S3 bucket
* Disabled "Block Public Access"
* Enabled ACL for public access
* Uploaded multiple HTML pages (Dashboard, Courses, Students etc..)
* Enabled static website hosting
* Configured index document

## Challenges Faced

* Initially received 403 Forbidden errors due to permission issues
* Needed to understand how public access works in S3

## Solutions

* Adjusted bucket permissions and policies to allow public read access
* Verified object-level accessibility

## Key Learnings

* S3 can serve as a static website host without a server
* Permissions (ACL vs bucket policy) are critical
* S3 behaves like a file storage system (case-sensitive, no server logic)

##Additional Observation

Even without enabling static website hosting, files could be accessed directly via S3 object URLs. This showed that S3 can serve files as a storage service, but static hosting is required for proper website behavior like default index routing and error handling.

## Improvements / Next Steps

* Host the same site using a web server (Nginx on EC2)
* Compare static hosting vs server-based hosting
