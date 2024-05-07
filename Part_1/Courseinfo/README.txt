must be installed:
node -v
npm -v

create project:
npx create-react-app youtube-course
cd youtube-course
npm start

create react app
PS C:\1_React_Helsinki> cd part1   (cd (change project))
PS C:\1_React_Helsinki\part1> npm run dev

----------------------------------------------------------

1.1 Course Information, Step 1

import React from 'react'

const App = () => {
  const course = 'Half Stack application development'
  const part1 = 'Fundamentals of React'
  const exercises1 = 10
  const part2 = 'Using props to pass data'
  const exercises2 = 7
  const part3 = 'State of a component'
  const exercises3 = 14

  return (
    <div>
    	<Header course = {course} />
	<Content part1 = {part1} part2 = {part2} part3 = {part3} exercises1 = {exercises1} exercises2 = {exercises2} exercises3 = {exercises3} />
	<Total exercises1 = {exercises1} exercises2 = {exercises2} exercises3 = {exercises3} />
  </div>
  )
}

const Header = (props) => {
  console.log(props)
  return (
    <>
      <h1>
        {props.course}
      </h1>
    </>
  )
}

const Content = (props) => {
  console.log(props)
  return(
    <>
    <p>
      {props.part1} {props.exercises1}
      </p>
    <p>
      {props.part2} {props.exercises2}
    </p>
    <p>
      {props.part3} {props.exercises3}
    </p>
    </>
  )
}

const Total = (props) => {
  console.log(props)
  return(
    <>
    <p>
    Total number of exercises {props.exercises1+props.exercises2+props.exercises3}
    </p>
    </>
  )
}

export default App

1.2 Course Information, Step 2

import React from 'react'

const App = () => {
  const course = 'Half Stack application development'
  const part1 = 'Fundamentals of React'
  const exercises1 = 10
  const part2 = 'Using props to pass data'
  const exercises2 = 7
  const part3 = 'State of a component'
  const exercises3 = 14

  return (
    <div>
		<Header course = {course} />
		<Content part1 = {part1} part2 = {part2} part3 = {part3} exercises1 = {exercises1} exercises2 = {exercises2} exercises3 = {exercises3} />
		<Total exercises1 = {exercises1} exercises2 = {exercises2} exercises3 = {exercises3} />
    </div>
  )
}

const Header = (props) => {
	return (
		<div>
			<h1>{props.course}</h1>
		</div>
	)
}

const Content = (props) => {
	return (
		<div>
      <Part part={props.part1} exercises={props.exercises1} />
      <Part part={props.part2} exercises={props.exercises2} />
      <Part part={props.part3} exercises={props.exercises3} />
    </div>
	)
}

const Part = (props) => {
  return (
    <p>
      {props.part} {props.exercises}
    </p>
  )
  }

  const Total = (props) => {
	return (
		<div>
			<p>Number of exercises {props.exercises1 + props.exercises2 + props.exercises3}</p>
		</div>
	)
}

export default App

1.3: Course Information, Step 3

import React from 'react'

const App = () => {
  const course = 'Half Stack application development'
  const part1 = {
    name: 'Fundamentals of React',
    exercises: 10
  }
  const part2 = {
    name: 'Using props to pass data',
    exercises: 7
  }
  const part3 = {
    name: 'State of a component',
    exercises: 14
  }

  return (
    <div>
      <h1>{course}</h1>
      	<p>{part1.name}: {part1.exercises}</p>
	<p>{part2.name}: {part2.exercises}</p>
	<p>{part3.name}: {part3.exercises}</p>
	<p>Number of exercises: {part1.exercises + part2.exercises + part3.exercises}</p>
    </div>
  )
}

export default App

1.4: Course Information, Step 4

import React from 'react'

const App = () => {
	const course = 'Half Stack application development'
	const parts = [
		{
      
		  name: 'Fundamentals of React',
		  exercises: 10
		},
		{
      
		  name: 'Using props to pass data',
		  exercises: 7
		},
		{
      
		  name: 'State of a component',
		  exercises: 14
		}
	]

	return (
		<div>
			<Header course={course} />
			<Content parts={parts} />
			<Total parts={parts} />
		</div>
	)
}

const Header = (props) => {
	return (
		<div>
			<h1>{props.course}</h1>
		</div>
	)
}

const Content = (props) => {
  console.log(props)
	const nameExercises = props.parts.map(item => (
		
			<div>
				<p> {item.name}: {item.exercises}</p>
			</div>
		)
  )
	
	return nameExercises
}

const Total = (props) => {
	let counter = 0
	
	const exrcisesTotal = props.parts.map( item=>( 
		
		counter = counter + item.exercises 
		
	))
	
	return (
		<div>
			<p>Number of exercises: {counter} </p>
		</div>
	)
}
	 
 
export default App

1.5: Course Information, Step 5

import React from 'react'

const App = () => {
  const course = {
    name: 'Half Stack application development',
    parts: [
      {
        name: 'Fundamentals of React',
        exercises: 10
      },
      {
        name: 'Using props to pass data',
        exercises: 7
      },
      {
        name: 'State of a component',
        exercises: 14
      }
    ]
  }

  return (
    <div>
      <h1>{course.name} </h1>
      <Content course={course} />
      <Total course={course} />
    </div>
  )
}

const Content = (props) => {
	const lists = props.course.parts.map(function(item) {
		return (
			<div>
				<p>{item.name}: {item.exercises}</p>
			</div>
		)
	})
	
	return lists
}

  const Total = (props) => {
    var score = 0
    
    const lists = props.course.parts.map(function(item) {
      
      score = score + item.exercises
      
      return score
    })
    
    return (
      <div>
        <p>Number of exercises: {score}</p>
      </div>
    )
  }

  
export default App
