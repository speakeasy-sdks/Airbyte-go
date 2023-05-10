<!-- Start SDK Example Usage -->
```go
package main

import(
	"context"
	"log"
	"airbyte-test"
	"airbyte-test/pkg/models/shared"
)

func main() {
    s := airbytetest.New()

    ctx := context.Background()
    res, err := s.Attempt.SaveStats(ctx, shared.SaveStatsRequestBody{
        AttemptNumber: 548814,
        JobID: 592845,
        Stats: shared.AttemptStats{
            BytesEmitted: airbytetest.Int64(715190),
            EstimatedBytes: airbytetest.Int64(844266),
            EstimatedRecords: airbytetest.Int64(602763),
            RecordsCommitted: airbytetest.Int64(857946),
            RecordsEmitted: airbytetest.Int64(544883),
            StateMessagesEmitted: airbytetest.Int64(847252),
        },
        StreamStats: []shared.AttemptStreamStats{
            shared.AttemptStreamStats{
                Stats: shared.AttemptStats{
                    BytesEmitted: airbytetest.Int64(623564),
                    EstimatedBytes: airbytetest.Int64(645894),
                    EstimatedRecords: airbytetest.Int64(384382),
                    RecordsCommitted: airbytetest.Int64(437587),
                    RecordsEmitted: airbytetest.Int64(297534),
                    StateMessagesEmitted: airbytetest.Int64(891773),
                },
                StreamName: "ipsa",
                StreamNamespace: airbytetest.String("delectus"),
            },
            shared.AttemptStreamStats{
                Stats: shared.AttemptStats{
                    BytesEmitted: airbytetest.Int64(272656),
                    EstimatedBytes: airbytetest.Int64(383441),
                    EstimatedRecords: airbytetest.Int64(477665),
                    RecordsCommitted: airbytetest.Int64(791725),
                    RecordsEmitted: airbytetest.Int64(812169),
                    StateMessagesEmitted: airbytetest.Int64(528895),
                },
                StreamName: "iusto",
                StreamNamespace: airbytetest.String("excepturi"),
            },
        },
    })
    if err != nil {
        log.Fatal(err)
    }

    if res.InternalOperationResult != nil {
        // handle response
    }
}
```
<!-- End SDK Example Usage -->