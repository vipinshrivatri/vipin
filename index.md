<html ng-app="resume">
  <head>
    <title>Vipin Shrivatri</title>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="The resume of Kent C. Dodds" />
    <meta name="keywords" content="Kent Dodds, kentcdodds, Kent C. Dodds, web developer, frontend developer" />
    <meta name="author" content="Kent C. Dodds" />

    <link href='http://fonts.googleapis.com/css?family=PT+Sans:400,700,400italic,700italic|PT+Sans+Narrow:400,700' rel='stylesheet' type='text/css'>
    <link href="styles/styles.css" rel="stylesheet">
    <!--
      If you're looking at this resume to judge my abilities, then please don't.
      I take my craft seriously, but this is one thing that I didn't spend a crazy
      amount of time on. If you're curious how I actually code, please see my
      github profile :-) https://github.com/kentcdodds
    -->
  </head>
  <body class="ng-cloak" ng-controller="MainCtrl">
    <div id="main-container">
      <h1>{{contact.name}}</h1>
   
      <section id="experience">
        <h2>Experience</h2>
        <div ng-repeat="xp in experience">
          <time>{{xp.timeRange}}</time>
          <a ng-href="{{xp.companyUrl}}">{{xp.company}}</a>
          <ul>
            <li ng-repeat="achievement in xp.achievements" ng-bind-html="achievement"></li>
          </ul>
        </div>
      </section>
      <section>
        <a href="#" ng-click="showExtras=!showExtras" class="show-more">
          <span ng-if="!showExtras">Show More ↓</span>
          <span ng-if="showExtras">Show Less ↑</span>
        </a>
        <div ng-show="showExtras">
          <div ng-repeat="xp in extraExperience">
            <time>{{xp.timeRange}}</time>
            <a ng-href="{{xp.companyUrl}}">{{xp.company}}</a>
       
          </div>
        </div>
      </section>
      <section id="skills-and-achievements">
        <h2>Skills & Achievements</h2>
        <ul>
          <li ng-repeat="item in skillsAndAchievements">
            <h3>{{item.title}}: </h3><span ng-bind-html="item.content"></span>
          </li>
        </ul>
      </section>
      <section id="education">
        <h2>Education</h2>
        <h3>{{education.degree}} | {{education.gpa}}</h3><time>{{education.graduationDate}}</time>
        <a ng-href="{{education.schoolUrl}}">{{education.school}}</a> | <a ng-href="{{education.collegeUrl}}">{{education.college}}</a>
        <ul>
          <li ng-repeat="item in education.items" ng-bind-html="item"></li>
        </ul>
      </section>
    </div>

    <script src="https://ajax.googleapis.com/ajax/libs/angularjs/1.4.5/angular.min.js"></script>

    <script src="vendor/ga.js"></script>


  </body>
</html>
