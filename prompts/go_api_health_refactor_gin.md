# Prompt — Go API: Refactor /health into internal/handlers (Gin + zerolog)

ROLE:
You are a senior software assistant helping a Mid-level Go backend engineer.

OBJECTIVE:
Refactor the existing Gin /health endpoint into internal/handlers, align the response to {"status":"ok"}, and keep behavior production-friendly.

CONTEXT:

- Current entrypoint is cmd/api/main.go.
- We use Gin (github.com/gin-gonic/gin) and zerolog (github.com/rs/zerolog/log).
- Config is loaded from our internal config package and provides:
  - cfg.Port
  - cfg.Env
  - cfg.ReadTimeout (time.Duration)
  - cfg.WriteTimeout (time.Duration)
- Current /health returns {"message":"Server listening on :8080"} but we want:
  - HTTP 200
  - JSON body: {"status":"ok"}
  - Content-Type: application/json
- Keep changes minimal and idiomatic.

INPUTS:
Current main.go:

```go
package main

import (
	"net/http"

	"github.com/diegotrujillor/go-portfolio-api/config"

	"github.com/gin-gonic/gin"
	"github.com/rs/zerolog/log"
)

func main() {
	cfg, err := config.Load()
	if err != nil {
		log.Fatal().Err(err).Msg("Failed to load configuration")
	}
	log.Info().Msgf("Loaded configuration: %+v", cfg)

	router := gin.Default()

	router.GET("/health", func(c *gin.Context) {
		log.Info().Msg("Received ping request")
		c.JSON(http.StatusOK, gin.H{
			"message": "Server listening on :8080",
		})
	})

	// Create HTTP server with config values
	server := &http.Server{
		Addr:         ":" + cfg.Port,
		Handler:      router,
		ReadTimeout:  cfg.ReadTimeout,
		WriteTimeout: cfg.WriteTimeout,
	}

	log.Info().Str("port", cfg.Port).Str("env", cfg.Env).Msg("Starting API server")
	if err := server.ListenAndServe(); err != nil {
		log.Fatal().Err(err).Msg("Failed to start API server")
	}
}
```

CONSTRAINTS:

- Use Gin + zerolog (do not remove them).
- Keep endpoint path: GET /health
- Response must be exactly: {“status”:“ok”}
- Use the configured port (cfg.Port) and timeouts.
- Avoid logging config values verbatim (do not log the entire cfg struct).
- Provide complete, compilable code.
- Keep handlers thin.

OUTPUT FORMAT:
Provide full contents for:

1. cmd/api/main.go
2. internal/handlers/health.go (new)
3. (Optional) internal/httpapi/router.go (only if you think it improves structure without over-engineering)

Also include:

- curl command to verify
- short note listing what changed (max 5 bullets)

SUCCESS CRITERIA:

- go run ./cmd/api starts successfully
- curl localhost:<PORT>/health returns {“status”:“ok”}
- Code is idiomatic and minimal
