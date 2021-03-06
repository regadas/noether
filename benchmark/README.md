
# noether-benchmark

This module describes benchmarking for the noether project.

## Run benchmark

* Open an sbt shell in the project root:

           sbt 

* Then switch to the subproject `noetherBenchmark`

        
        sbt:noether> project noetherBenchmark
        
        # Run all the benchmarks..
        sbt:noetherBenchmark> jmh:run .*
        
        # Run specific benchmark (CalibrationHistogram benchmark)
        sbt:noetherBenchmark> jmh:run .*CalibrationHistogram.*

### Example

        jmh:run -t1 -f1 -wi 2 -i 3 .*Calibration.*


The output should look something like this: 


    [info] Benchmark                                                       (lowerBound)  (nbBucket)  (nbElement)  (upperBound)   Mode  Cnt          Score            Error  Units
    [info] CalibrationHistogramCreateBenchmark.createCalibrationHistogram           0.1         100          100           0.2  thrpt    3  354495958,865 ±   19222766,245  ops/s
    [info] CalibrationHistogramCreateBenchmark.createCalibrationHistogram           0.1         100          100           0.4  thrpt    3  354159610,708 ±   19887361,006  ops/s
    [info] CalibrationHistogramCreateBenchmark.createCalibrationHistogram           0.1         100          100           0.5  thrpt    3  353401735,022 ±    9100858,662  ops/s
    [info] CalibrationHistogramCreateBenchmark.createCalibrationHistogram           0.1         100         1000           0.2  thrpt    3  352173891,822 ±   26480103,060  ops/s
    [info] CalibrationHistogramCreateBenchmark.createCalibrationHistogram           0.1         100         1000           0.4  thrpt    3  352870170,909 ±   21414322,507  ops/s
    [info] CalibrationHistogramCreateBenchmark.createCalibrationHistogram           0.1         100         1000           0.5  thrpt    3  354991297,412 ±   37282062,985  ops/s
    [info] CalibrationHistogramCreateBenchmark.createCalibrationHistogram           0.1         100         3000           0.2  thrpt    3  352385150,389 ±   25101115,471  ops/s
    [info] CalibrationHistogramCreateBenchmark.createCalibrationHistogram           0.1         100         3000           0.4  thrpt    3  355695107,774 ±   27960629,389  ops/s
    [info] CalibrationHistogramCreateBenchmark.createCalibrationHistogram           0.1         100         3000           0.5  thrpt    3  353599563,110 ±   35675109,158  ops/s
    [info] CalibrationHistogramCreateBenchmark.createCalibrationHistogram           0.1         200          100           0.2  thrpt    3  354172265,477 ±   29726736,262  ops/s
    [info] CalibrationHistogramCreateBenchmark.createCalibrationHistogram           0.1         200          100           0.4  thrpt    3  353407712,527 ±   15231956,560  ops/s
    [info] CalibrationHistogramCreateBenchmark.createCalibrationHistogram           0.1         200          100           0.5  thrpt    3  355430167,821 ±   53204747,979  ops/s
    ...
