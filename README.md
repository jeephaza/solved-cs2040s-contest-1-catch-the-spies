Download Link: https://assignmentchef.com/product/solved-cs2040s-contest-1-catch-the-spies
<br>
I think CS2040S has been compromised! We have just received information that hidden among the <em>N </em>students of CS2040S are <em>K </em>spies! Your job is to identify all the spies.

You can send a group of (≥ <em>K</em>) students on a mission. If all <em>K </em>spies are on the same mission, they will have a secret meeting to plot their evil plots. For any set of students that are sent on a mission together, you will learn if a secret meeting occurred, or not. You learn nothing else.

As discussed in lecture, it just so happens that 122 is the minimum number of missions needed for

<em>N </em>= 1024<em>,K </em>= 17. (Can you prove that?)

<h1>1           Code Briefing</h1>

<h2>1.1         Interface Descriptions</h2>

Within code.zip, you should see the IMissionControl interface:

public interface IMissionControl { public boolean sendForMission(int[] mission);

}

The interface provides the following method for you to use in your solution:

<ul>

 <li>boolean sendForMission(int[] mission):</li>

</ul>

Sends a group of students on a mission and returns true if there’s a secret meeting, false otherwise.

mission should be an array of length <em>N </em>of 0’s and 1’s (represented as integers), where a 1 at index <em>i </em>means that student <em>i </em>is sent on the mission. As per the description above, the array needs to have ≥ <em>K </em>1’s.

For example, for <em>N </em>= 5<em>,K </em>= 2, mission = {1<em>,</em>0<em>,</em>1<em>,</em>0<em>,</em>0} means that students 0 and 2 are sent on the mission.

1

In the tasks below, your job is to implement the IFindSpies interface:

public interface IFindSpies { public int[] findSpies(int N, int k, IMissionControl missionControl);

}

The interface requires you to support the following method:

<ul>

 <li>int[] findSpies(int N, int k, IMissionControl missionControl):</li>

</ul>

Returns an array of length <em>N </em>of 0’s and 1’s (represented as integers), where a 1 at index <em>i </em>means that student <em>i </em>is a spy. As per the description above, the array should have <em>K </em>1’s.

For example, for <em>N </em>= 5<em>,K </em>= 2, {1<em>,</em>0<em>,</em>1<em>,</em>0<em>,</em>0} means that students 0 and 2 are spies. You are given N: the total number of students, k: the total number of spies, and missionControl as described above for you to call sendForMission.

<h2>1.2         Testing</h2>

To test your implementation, you can run the main function in RunContest.java. If your implementation is correct (returns the correct spy bitmap), you should see in your console relevant information about the performance of your algorithm. Otherwise, you should see an Exception being thrown. Feel free to change bitmap to experiment with different <em>N </em>and <em>k</em>.

<h1>2           Tasks</h1>

<em>Problem 1: </em>For any <em>N </em>students and <em>K </em>spies, what is the minimum number of missions that we need? Implement an algorithm in FindSpyMinimumSteps.java that attempts to achieve this minimum number of missions.

<em>Bonus Optional: </em>What is the asymptotic upper bound? Can you prove it?

<em>Problem 2: </em>Suppose it costs $1 to send each student on a mission. What is the minimum amount that we need to spend? Implement an algorithm in FindSpyLowestCost.java that attempts to achieve the minimum cost required to identify all <em>K </em>spies.