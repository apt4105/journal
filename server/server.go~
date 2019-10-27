package main

import (
	"fmt"
	"net/http"
	"strings"
	"os"
)

func main() {
	fmt.Println("vim-go")

	fs := http.FileServer(http.Dir("/"))

	http.HandleFunc("/", func(w http.ResponseWriter, r *http.Request) {
		if strings.HasPrefix(r.URL.Path, "/asset") {
			s := strings.Split(r.URL.Path, "/")
			fmt.Println(s[2])
			//check if User dir exists
			if _, err := os.Stat("asset/"+s[2]+"/"); os.IsNotExist(err) {
				fmt.Fprint(w, "No such User, " + s[2]+".")
				return
			}

			//if _, err := os.Stat("//")
			//!os.IsNotExist(err) {
			// path/to/whatever exists
			//}
			//http.StripPrefix("/asset", fs).ServeHTTP(w, r)
			//if _,  
			return
		}else {
			fmt.Fprintf(w, "%s %s", r.Method, r.URL.Path)
		}
	})

	http.Handle("/static/", http.StripPrefix("/static/", fs))
	http.ListenAndServe(":8080", nil)

}

