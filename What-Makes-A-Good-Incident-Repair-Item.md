# What Makes a Good PIR Repair Item?

Incident repair items are issues that can be tracked in JIRA and represent concrete actions or measures that would have prevented the incident or minimized customer disruption. Ideally, repair items should be scoped so they can be completed within a 90-day SLA.

## A Well-Written Repair Item Is:

* __Timely__ – The purpose of a repair item is to reduce risk in the short term. Items that will take months should be logged as risks with a mitigation plan, rather than as repair items.
* __Actionable__ – A repair item should clearly describe what needs to be done to reduce risk. “More research” is not a repair item, nor is a “plan to make a plan.”
* __Specific__ – A repair item shouldn't attempt to build an entirely new service, program, bureaucratic process, or simply "improve communication" between teams.
* __Proactive__ – Improving run book documentation to better handle the same incident in the future is not a repair item. A repair item fixes a problem so the incident does not happen again.
* __Related to the incident__ – Repair items are not a collection of tangential nice-to-have fixes; they address a specific incident. There should be a clear connection showing how implementing a repair item will prevent the incident from recurring. If tangential fixes are identified, record them in the backlog and prioritize them normally.
* __Properly scoped__ – Repair items can fix technical problems or address specific process failures, but shouldn’t attempt to restructure entire organizations. A repair item should aim to fix the general class of an incident, not just one specific instance, but shouldn’t be so broad that it tries to fix all possible incidents. When in doubt, lean toward specificity.

## Repair Items vs. Resiliency Projects

During a PIR, you may discover opportunities for long-term improvements, investigations, research, or spikes, which can be logged in JIRA as general improvements. If long-term changes, significant refactors, or other large-effort changes are recommended by a PIR, these should be incorporated directly into the roadmap with product and engineering management.

If an issue cannot be resolved quickly, it is not a repair item —- those are future-scheduled resiliency projects. Teams should honestly ask themselves: “Is there something smaller I could do as a repair item instead of putting everything into ‘future re-architecture’?” Future ambitions must not prevent real and practical repair items from being addressed in the present.

## Categorizing Work After an Incident

1. Does the idea meet the above requirements and can it be executed quickly?
   1. You’ve identified a repair item!
   1. Add the repair item to your PIR.
   1. Schedule it in the next few sprints.

1. Is the idea something that “needs to be done,” but is not immediately needed to prevent another incident?
   1. You’ve identified necessary work.
   1. Create a story in the backlog and schedule it as you normally would.
   1. Don’t tag it as a repair item.

1. Is the idea to replace an entire system, or a major overhaul of a component, service, or system?
   1. You’ve identified an epic.
   1. Plan the work and schedule it according to your quarterly planning process.

1. Is the idea a “plan to make a plan”?
   1. Take some time now to make the plan as part of your PIR.
   1. Classify the outcomes of that plan as repair items, future work items, or epics.
