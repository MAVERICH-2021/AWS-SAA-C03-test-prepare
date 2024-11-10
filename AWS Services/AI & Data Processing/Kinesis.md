### Data Streams (KDS)
   - **Real-Time Data Ingestion**: Allows real-time ingestion and processing of massive data streams (such as log files, social media, IoT data).
   - ==**Customizable Data Processing**:== Enables users to build custom applications or utilize Lambda to process data in real-time.
   - **Scaling Flexibility**: Supports on-demand and provisioned modes to scale throughput based on demand.
   - **Data Retention**: Allows retention of streaming data for up to 7 days by default (with extended options), enabling replay of data for analytics.

**more control and flexibility** over streaming data, allowing you to build real-time applications that consume and process data streams.


### Data Firehose
   - **Real-Time Data Transformation and Loading**: Simplifies loading data streams into data stores like S3, [[Redshift]], Elasticsearch, and Splunk.
   - **Automatic Scaling**: Manages scaling automatically based on the incoming data volume.
   - **Data ==Transformation== with Lambda**: Enables data transformation, format changes, and compression before delivering to a target.
   - **Easy Setup and Maintenance-Free**: ==Fully managed ==service requiring no setup or maintenance of streaming infrastructure.

**ingests, transforms, and delivers data** in ==near-real time== to destinations like S3, Redshift, OpenSearch, or Splunk.

### Data Analytics
   - **SQL-Based Stream Processing**: Uses standard SQL to process, transform, and analyze streaming data in real-time.
   - **Seamless Integration with Data Streams and Firehose**: Directly processes data from Kinesis Data Streams and Data Firehose for insights.
   - **Real-Time Analytics and Aggregation**: Enables real-time analytics for applications like anomaly detection, clickstream analysis, and IoT monitoring.
   - **Windowed Analysis**: Allows for analysis on time windows, such as tumbling and sliding windows, for more sophisticated real-time analysis.

### Video Streams
   - **Real-Time Video Streaming and Processing**: Handles video and audio data for real-time analysis or storage.
   - **Integration with ML Services**: Integrates with services like Amazon Rekognition for video analytics, computer vision, and real-time monitoring.
   - **Secure Video Data Storage**: Supports secure storage, encryption, and access control for video streams.
   - **Playback and Retrieval**: Enables playback of video streams for applications such as monitoring, security, and playback on demand.

