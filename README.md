# scala
Practical No.1

object hello{
    def main(arg: Array[String]): Unit = {
        println("Welcome to SYDS!!!")
    }
}

Practical no.2

object maths {
    def main(args: Array[String]): Unit = {
        val a: Int = 20
        val b: Int = 5
        val marks: Double = 50.6
        val name: String = "Anu"
        val addition = a + b
        val subtraction = a - b
        val multiplication = a * b
        val division = a / b
        
        println("Name: " + name)
        println("First number: " + a)
        println("Second number: " + b)
        println("Marks: " + marks)
        println("Addition = " + addition)
        println("Subtraction = " + subtraction)
        println("Multiplication = " + multiplication)
        println("Division = " + division)
    }
}

Practical No.3

object stat {
    def main(args: Array[String]): Unit = {
        val data = Array(10, 20, 30, 20, 40)
        val mean = data.sum.toDouble / data.length
        val sorted = data.sorted
        val median = sorted(sorted.length / 2)
        val mode = data.groupBy(x => x).maxBy(x => x._2.length)._1
        
        println("Mean: " + mean)
        println("Median: " + median)
        println("Mode: " + mode)
    }
}

Practical No.4

object variance {
    def main(args: Array[String]): Unit = {
        val data = Array(10, 20, 30, 40, 50)
        val mean = data.sum.toDouble / data.length
        val variance = data.map(x => (x - mean) * (x - mean)).sum / data.length
        val standardDeviation = Math.sqrt(variance)
        
        println("Mean: " + mean)
        println("Variance: " + variance)
        println("Standard Deviation: " + standardDeviation)
    }
}

Practical no.5

write this code in "built.sbt" file:
val scala3Version = "3.8.4"

lazy val root = project
  .in(file("."))
  .settings(
    name := "scala3",
    version := "0.1.0-SNAPSHOT",

    scalaVersion := scala3Version,

    libraryDependencies += "org.scalameta" %% "munit" % "1.3.2" % Test,
    libraryDependencies += "org.scalanlp" %% "breeze" % "2.1.0"
  )

This is main file "breeze.scala":

import breeze.linalg._

object breeza{
    def main(args: Array[String]): Unit = {
        val v1 = DenseVector(1.0, 2.0, 3.0)
        val v2 = DenseVector(4.0, 5.0, 6.0)

        val sum = breeze.linalg.sum(v1)
        val mean = breeze.stats.mean(v1)
        val dotProduct = v1 dot v2

        println("Vector 1: " + v1)
        println("Vector 2: " + v2)
        println("Sum: " + sum)
        println("Mean: " + mean)
        println("Dot Product: " + dotProduct)
    }
}

Practical no.6

write this code in "built.sbt" file:
val scala3Version = "3.8.4"

lazy val root = project
  .in(file("."))
  .settings(
    name := "scala3",
    version := "0.1.0-SNAPSHOT",

    scalaVersion := scala3Version,

    libraryDependencies += "org.scalameta" %% "munit" % "1.3.2" % Test,
    libraryDependencies += "org.scalanlp" %% "breeze" % "2.1.0"
  )

This is main file "BreezeMatrix.scala":
import breeze.linalg._

object BreezeMatrix {
    def main(args: Array[String]): Unit = {
        val matrix = DenseMatrix(  (1.0, 2.0), (3.0, 4.0))

        println("Matrix:")
        println(matrix)

        println("\nTranspose:")
        println(matrix.t)

        println("\nDeterminant:")
        println(det(matrix))
    }
}

Practical no.7

first create file named "data.csv" in VS code Explorer and add values. Note:(create csv file outside of any folder) :-
Marks
75
82
68
90
56
95
72
88
64
79

this is the main file "csvstatistics":
import scala.io.Source

object CSVStatistics {
    def main(args: Array[String]): Unit = {

        val data= Source.fromFile("data.csv").getLines().drop(1).map(_.toDouble).toList

        val count = data.length
        val sum = data.sum
        val average = sum / count
        val maximum = data.max
        val minimum = data.min

        println("Count: " + count)
        println("Sum: " + sum)
        println("Average: " + average)
        println("Maximum: " + maximum)
        println("Minimum: " + minimum)
    }
}

Practical no.8

write this code in "built.sbt" file:
val scala3Version = "3.8.4"

lazy val root = project
  .in(file("."))
  .settings(
    name := "scala3",
    version := "0.1.0-SNAPSHOT",

    scalaVersion := scala3Version,

    libraryDependencies += "org.scalameta" %% "munit" % "1.3.2" % Test,
    libraryDependencies ++= Seq("org.scalanlp" %% "breeze" % "2.1.0",
    "org.scalanlp" %% "breeze-viz" % "2.1.0")
  )

This is main file :

import breeze.linalg._
import breeze.plot._
import java.awt.Color   


object DataVisualization {
    def main(args: Array[String]): Unit = {

        val data = DenseVector(10.0, 20.0, 30.0, 20.0, 40.0, 30.0, 50.0)

        val x = DenseVector(1.0, 2.0, 3.0, 4.0, 5.0)
        val y = DenseVector(2.0, 4.0, 6.0, 8.0, 10.0)

        val f = Figure("Histogram and Scatter Plot")

        val p1 = f.subplot(2, 1, 0)
        val h = hist(data, 5)
        p1 += h
        p1.title = "Histogram"
        p1.xlabel = "Values"
        p1.ylabel = "Frequency"

        val p2 = f.subplot(2, 1, 1)
        val s = plot(x, y, '.')
        p2 += s
        p2.title = "Scatter Plot"
        p2.xlabel = "X Values"
        p2.ylabel = "Y Values"

        f.refresh()
    }
}

Practical no.9

write this code in "built.sbt" file:
val scala3Version = "3.8.4"

lazy val root = project
  .in(file("."))
  .settings(
    name := "scala3",
    version := "0.1.0-SNAPSHOT",

    scalaVersion := scala3Version,

    libraryDependencies += "org.scalameta" %% "munit" % "1.3.2" % Test,
    libraryDependencies ++= Seq("org.scalanlp" %% "breeze" % "2.1.0",
    "org.scalanlp" %% "breeze-viz" % "2.1.0")
  )

This is main file :

import breeze.linalg._
import breeze.stats._

object LinearRegression {
    def main(args: Array[String]): Unit = {

        val x = DenseVector(1.0, 2.0, 3.0, 4.0, 5.0)
        val y = DenseVector(2.0, 4.0, 5.0, 4.0, 5.0)

        val xMean = mean(x)
        val yMean = mean(y)

        val numerator = sum((x - xMean)*:*(y - yMean))
        val denominator = sum((x - xMean)*:*(x - xMean))
        val slope = numerator / denominator

        val intercept = yMean - slope * xMean

        println("Slope (m): " + slope)
        println("Intercept (c): " + intercept)

        val xNew = 6.0
        val prediction = slope * xNew + intercept

        println("Predicted value for x = 6: " + prediction)
    }
}





















