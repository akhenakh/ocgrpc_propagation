# ocgrpc_propagation
ocgrpc opencensus gRPC tools with propagation from Jaeger

This a copy of [ocgrpc](https://github.com/census-instrumentation/opencensus-go/tree/master/plugin/ocgrpc) adding `uber-trace-id` compatibility traces.

Use it exactly like `ocgrpc` but it will propagate incoming Jaeger traces.
```
ocgrpc_propag "github.com/akhenakh/ocgrpc_propagation"

gsrv := grpc.NewServer(
  grpc.StatsHandler(&ocgrpc_propag.ServerHandler{}),
)
```

## Known issues
Due to conflit in registering views, you can't import `zpages` anymore.
