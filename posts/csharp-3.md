---
title: "Creating Random Numbers and Handling Floats in C# Unity"
date: "2020-05-27"
---
```csharp
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class QuizCalculator : MonoBehaviour
{
    // Start is called before the first frame update
    public float quiz1, quiz2, quiz3, quiz4, quiz5;



    void Start()
    {   
        //Random.Range creates a number between the values you give it
        quiz1 = Random.Range(0, 100f);
        quiz2 = Random.Range(0, 100f);
        quiz3 = Random.Range(0, 100f);
        quiz4 = Random.Range(0, 100f);
        quiz5 = Random.Range(0, 100f);

        float average = (quiz1 + quiz2 + quiz3 + quiz4 + quiz5) / 5;
        // The final / 100 is basically telling you how many decimal places to round by
        // If you wanted to round by 3 decimal places your would do / 1000
        average = Mathf.Round(average * 100f) / 100f;
        Debug.Log("Average quiz score: " + average);
    }

    // Update is called once per frame
    void Update()
    {
        
    }
}
```