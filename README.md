# Ad Conversions via Oblivious Shuffling

## Sample Input Dataset
The data folder contains 2 input datasets for the bucketization protocol. Each of them contains 1,000,000 attribution keys for the histogram aggregation.
The data is drawn from Zipf distribution with the parameter 1.03 and domain size (support) 1,048,576. The size of the keys are 32-bit and 128-bit
respectively.

## Benchmarks
We test and report the performance of the bucketization protocol. The datasets above are used as the inputs. The output is a histogram
aggregated by the keys. We consider the threshold parameter to prune the layered bucketization. The results achieve differential privacy.
The experiments are done in three Microsoft Azure Standard D8s v4 machines each equipped with 8vCPU and 32GiB RAM. Two of them are located
at the us-west region and one of them is located at us-east region. The round-trip delay between the west and east is 64ms.

| key size (bits) | #keys | domain size | threshold | running time (seconds) |
| --------------- | ----- | ----------- | --------- | ---------------------- |
| 32  | 1,000,000 | 1,048,576 | 200 | 9.89   |
| 128 | 1,000,000 | 1,048,476 | 500 | 352.14 |
