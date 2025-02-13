````
package main

import (
"net/http"
"time"

	"github.com/gin-gonic/gin"
)

func main() {
// 创建一个默认的路由引擎
r := gin.Default()

	// 定义一个 GET 接口，路径为 "/current-time"
	r.GET("/current-time", func(c *gin.Context) {
		// 获取当前时间
		currentTime := time.Now().Format("2006-01-02 15:04:05") // 格式化为 YYYY-MM-DD HH:MM:SS

		// 返回 JSON 响应
		c.JSON(http.StatusOK, gin.H{
			"time": currentTime,
		})
	})

	// 启动服务，默认在 0.0.0.0:8080 启动服务
	r.Run()

}
````
