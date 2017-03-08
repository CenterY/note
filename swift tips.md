1. 操作数字不能使用混合类型,必须强转

		let hourlyRate = 19.5		let hoursWorked = 10		let totalCost = hourlyRate * Double(hoursWorked)
2. tuples

		# 索引		let coordinates: (Int, Int) = (2, 3)		let x: Int = coordinates.0		let y: Int = coordinates.1
		# 标签
		let coordinatesNamed: (x: Int, y: Int) = (2, 3)
		let x: Int = coordinatesNamed.x		let y: Int = coordinatesNamed.y
       
        # 一次访问多个
         let coordinates3D: (x: Int, y: Int, z: Int) = (2, 3, 1)		 let (x, y, z) = coordinates3D
         printf(x)		 3. 移位运算
   		# a 左移n位 = a * 2^n
  		# 右移除以2^n
  		
4. switch

		let coordinates: (x: Int, y: Int, z: Int) = (3, 2, 5)		switch (coordinates) {		case (0, 0, 0): // 1 			print("Origin")		case (_, 0, 0): // 2 			 print("On the x-axis.")		case (0, _, 0): // 3 			 print("On the y-axis.")		case (0, 0, _): // 4  			print("On the z-axis.")		default:        // 5  			print("Somewhere in space")		}
		
		let coordinates: (x: Int, y: Int, z: Int) = (3, 2, 5)		switch (coordinates) {		case (0, 0, 0):  		print("Origin")		case (let x, 0, 0):  		print("On the x-axis at x = \(x)")		case (0, let y, 0):  			print("On the y-axis at y = \(y)")		case (0, 0, let z):  			print("On the z-axis at z = \(z)")		case (let x, let y, let z): 			print("Somewhere in space at x = \(x), y = \(y), z = \(z)")		}
		
		let coordinates: (x: Int, y: Int, z: Int) = (3, 2, 5)		switch (coordinates) {		case (let x, let y, _) where y == x:  			print("Along the y = x line.")		case (let x, let y, _) where y == x * x:  			print("Along the y = x^2 line.")		default:			break		}
		let number = 10		switch (number) {		case let x where x % 2 == 0:  			print("Even")		default:  		print("Odd")		}
		5. 下划线标识忽略
6. 循环
 		var sum = 0		rowLoop: for row in 0..<8 {  		columnLoop: for column in 0..<8 {   		if row == column {    		continue rowLoop    	}    	sum += row * column  		}		}

7. func

        # 默认参数值
		func printMultipleOf(multiplier: Int, and andValue: Int = 1) {  			print("\(multiplier) * \(andValue) = \(multiplier * andValue)")		}		printMultipleOf(4) 
		
        # pass-by-value
        func incrementAndPrint(var value: Int) {  			value++ 			 print(value)		}
		var value = 5		incrementAndPrint(value)		print(value)
		
		It prints the following:		 6 		 5
		 
		 # pass-by-reference		 func incrementAndPrintInOut(inout value: Int) {  				value++ 			 print(value) 		 }
 		 var value = 5		 incrementAndPrintInOut(&value)		 print(value)
		 
		 It prints the following:		  6 
		  6
		  
8. array
			
		for (index, playerName) in players.enumerate() {  			print("\(index + 1). \(playerName)")		}		// > 1. Anna		// > 2. Brian		// > 3. Craig		// > 4. Donna		// > 5. Eli		// > 6. Franklin
		
 		let sum = scores.reduce(0, combine: +)		print(sum)		// > 21		This is the same as writing let sum = 0 + scores[0] + scores[1] + ... 			+ scores[5]
 
9. assert	 