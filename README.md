# Ad Conversions via Oblivious Shuffling

## Sample Input Dataset
The data folder contains 2 input datasets for the bucketization protocol. Each of them contains 1000000 attribution keys for the histogram aggregation.
The data is drawn from Zipf distribution with the parameter 1.03 and domain size (support) 1048576. The size of the keys are 32-bit and 128-bit
respectively.

## Benchmarks
We test and report the performance of the bucketization protocol[1]. The datasets above are used as the inputs. The output is a histogram
aggregated by the keys. We consider the threshold parameter to prune the layered bucketization.

The results achieve (\epsilon,\delta)-differential privacy with \epsilon=1 and \delta=2^{-40}. Additionally, we set M=81 for 32-bit keys in
2-layer bucketization and M=405 for 128-bit keys in 8-layer bucketization. The detailed analysis can be found at [1].

The experiments are done in 3 Microsoft Azure Standard D8s v4 machines each equipped with 8vCPU and 32GiB RAM. Two of them are located
at the us-west region and one of them is located at us-east region. The round-trip delay between the west and east is 64ms.

| key size (bits) | #keys | domain size | threshold | running time (seconds) |
| --------------- | ----- | ----------- | --------- | ---------------------- |
| 32  | 1000000 | 1048576 | 200 | 9.89   |
| 128 | 1000000 | 1048576 | 500 | 352.14 |

## References
[1] Aggregate Measurement via Oblivious Shuffling. Erik Anderson, Melissa Chase, F. Betul Durak, Esha Ghosh, Kim Laine, Chenkai Weng. [https://eprint.iacr.org/2021/1490](https://eprint.iacr.org/2021/1490).
