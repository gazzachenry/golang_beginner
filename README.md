package main

import "fmt"

func main() {
    // Khởi tạo slice
    s := []int{1, 2, 3, 4, 5}
    fmt.Println("Initial slice:", s)

    // Thêm phần tử vào slice
    s = append(s, 6, 7)
    fmt.Println("Slice after appending:", s)

    // Tạo slice từ mảng
    arr := [5]int{10, 20, 30, 40, 50}
    s2 := arr[1:4]
    fmt.Println("Slice from array:", s2)

    // Duyệt qua slice
    fmt.Println("Elements in slice:")
    for _, value := range s {
        fmt.Println(value)
    }

    // Sử dụng hàm make để tạo slice
    s3 := make([]int, 5)
    fmt.Println("Slice created with make:", s3)

    // Thay đổi phần tử trong slice
    s3[0] = 100
    fmt.Println("Slice after modification:", s3)

    // In chiều dài và dung lượng của slice
    fmt.Println("Length and capacity of slice s3:", len(s3), cap(s3))
}

# Slice of slices 
package main

import (
	"fmt"
	"strings"
)

func main() {
	// Create a tic-tac-toe board.
	board := [][]string{
		[]string{"_", "_", "_"},
		[]string{"_", "_", "_"},
		[]string{"_", "_", "_"},
	}

	// The players take turns.
	board[0][0] = "X" //[dòng] - [cột]
	board[2][2] = "O"//[dòng] - [cột]
	board[1][2] = "X"//[dòng] - [cột]
	board[1][0] = "O"//[dòng] - [cột]
	board[0][2] = "X"//[dòng] - [cột]
	board[1][1] = "T"

	for i := 0; i < len(board); i++ {
		fmt.Printf("%s\n", strings.Join(board[i], " "))
	}
}
