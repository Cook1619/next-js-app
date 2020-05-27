---
title: "Basic Unity Methods with Variables"
date: "2020-05-26"
---

```csharp
public class TipCalculator : MonoBehaviour
{
    // Start is called before the first frame update
    public int bill = 40;
    public float tip = 20.0f;
    public float totalAmount;
    void Start()
    {
        //tipAmount is a local variable to this methods
        float tipAmount = bill * (tip / 100);
        totalAmount = bill + tipAmount;
        Debug.Log("Your bill is: " + bill + " and your tip amount is: " + tipAmount + " so you owe " + totalAmount);
    }

    // Update is called once per frame
    void Update()
    {
        //This is where you would want to listen to keyboard clicks
    }
}
```