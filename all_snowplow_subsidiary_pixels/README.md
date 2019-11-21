# Snowplow Analytics for Thor Industries

<img src="https://d3i6fms1cm1j0i.cloudfront.net/github-wiki/images/snowplow-new-logo-large.png"
 alt="Snowplow logo" title="Snowplow" align="right" />

 ## Pixel Installation

 You will install the Thor Analytics pixel just like you'd install Google Analytics or the Facebook Pixel.

 Please follow these instructions.

 **Install with Google Tag Manager** If you're currently using Google Tag Manager you can easily deploy your Thor Analytics pixel.

 1. Create a new Custom HTML Tag
 2. Copy and paste the full script into the Custom HTML Window
 3. Add a trigger to fire the pixel on All Pages

 **Non Tag Manager Installation** If you do not have a Tag Manager installed on your website, you may hard code the Thor Analytics pixel into the **head** section of all pages on your website.

 Please validate that the pixel is correctly added to ALL pages on your website to make sure data is properly collected.

Snowplow is an enterprise-strength marketing and product analytics platform. It does four things:

1. Identifies your users, and tracks the way they engage with your website.
2. Stores your users' behavioural data in a scalable "event data warehouse" owned by Thor Industries: Data will be stored in a secure high-performance Snowflake database. You will be granted access to your website data upon request.
3. Lets you leverage the biggest range of tools to analyze that data, including big data tools (e.g. Spark) via EMR or more traditional tools e.g. Looker, PowerBI, Mode, Superset, Re:dash to analyze your data.
4. Allows you to easily connect additional data sources to better understand prospect journeys, what marketing is effective, what website content is compelling, and answer other key questions.

Key Benefits:
1. Granular and robust event data, allowing in-depth customer journey mapping.
2. Cookies persist longer than 24 hours / 7 days on Safari, allowing you to track longer customer journeys.
3. Understand the performance of Thor's referral traffic to you, allowing better funneling of the correct new prospects for your brand.

**To find out more, please check out the [Snowplow website][website] and the [Snowplow wiki][wiki].**

## Snowplow technology 101

![architecture][architecture-image]

To briefly explain these six sub-systems:

* **Trackers** fire Snowplow events. Currently we have 12 trackers, covering web, mobile, desktop, server and IoT. The web pixel will be provided to you.
* **Collectors** receive Snowplow events from trackers. Currently we have three different event collectors, sinking events either to Amazon S3, Apache Kafka or Amazon Kinesis
* **Enrich** cleans up the raw Snowplow events, enriches them and puts them into storage. Currently we have a Hadoop-based enrichment process, and a Kinesis- or Kafka-based process
* **Storage** is where the Snowplow events live. Currently we store the Snowplow events in a flatfile structure on S3, and in the Redshift and Postgres databases
* **Data modeling** is where event-level data is joined with other data sets and aggregated into smaller data sets, and business logic is applied. This produces a clean set of tables which make it easier to perform analysis on the data. We have data models for Redshift and **[Looker][looker]**
* **Analytics** are performed on the Snowplow events or on the aggregate tables.

**For more information on the current Snowplow architecture, please see the [Technical architecture][architecture-doc]**.

## Copyright and license

Snowplow is copyright 2012-2019 Snowplow Analytics Ltd.

Licensed under the **[Apache License, Version 2.0][license]** (the "License");
you may not use this software except in compliance with the License.

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

[travis-image]: https://travis-ci.org/snowplow/snowplow.png?branch=master
[travis]: http://travis-ci.org/snowplow/snowplow

[release-image]: https://img.shields.io/badge/release-116_Madara_Rider-orange.svg?style=flat
[releases]: https://github.com/snowplow/snowplow/releases

[license-image]: http://img.shields.io/badge/license-Apache--2-blue.svg?style=flat
[license]: http://www.apache.org/licenses/LICENSE-2.0

[gitter-image]: https://badges.gitter.im/snowplow/snowplow.svg
[gitter]: https://gitter.im/snowplow/snowplow?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge

[website]: http://snowplowanalytics.com
[wiki]: https://github.com/snowplow/snowplow/wiki
[architecture-image]: https://d3i6fms1cm1j0i.cloudfront.net/github-wiki/images/snowplow-architecture.png
[architecture-doc]: https://github.com/snowplow/snowplow/wiki/Technical-architecture
[talk-to-us]: https://github.com/snowplow/snowplow/wiki/Talk-to-us
[contributing]: ./CONTRIBUTING.md

[setup]: https://github.com/snowplow/snowplow/wiki/Setting-up-SnowPlow
[tech-docs]: https://github.com/snowplow/snowplow/wiki/SnowPlow%20technical%20documentation
[tracker-protocol]: https://github.com/snowplow/snowplow/wiki/snowplow-tracker-protocol
[collector-logs]: https://github.com/snowplow/snowplow/wiki/Collector-logging-formats
[data-structure]: https://github.com/snowplow/snowplow/wiki/canonical-event-model
[looker]: http://www.looker.com/

[techdocs-image]: https://d3i6fms1cm1j0i.cloudfront.net/github/images/techdocs.png
[setup-image]: https://d3i6fms1cm1j0i.cloudfront.net/github/images/setup.png
[roadmap-image]: https://d3i6fms1cm1j0i.cloudfront.net/github/images/roadmap.png
[contributing-image]: https://d3i6fms1cm1j0i.cloudfront.net/github/images/contributing.png

[techdocs]: https://github.com/snowplow/snowplow/wiki/SnowPlow-technical-documentation
[setup]: https://github.com/snowplow/snowplow/wiki/Setting-up-SnowPlow
[roadmap]: https://github.com/snowplow/snowplow/wiki/Product-roadmap
[contributing]: https://github.com/snowplow/snowplow/wiki/Contributing
