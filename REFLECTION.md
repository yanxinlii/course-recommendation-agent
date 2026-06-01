
# Reflection

## What Worked

The agent successfully used typed tools to check prerequisites and identify policy risks.

Structured outputs made evaluation easier because each response followed the same schema.

The guardrail correctly blocked course substitution requests before the advisor agent was executed.

## What Failed

Initially, the search_courses tool caused tool loops and produced MaxTurnsExceeded errors.

The first version of the course catalog was incomplete, causing the agent to incorrectly report that some courses did not exist.

One evaluation case produced an inconsistency where overload risk was detected but credits_this_term was returned as 0.

## Improvements

The tool loop issue was reduced by limiting tool usage and simplifying agent instructions.

The course catalog and prerequisite table were expanded and corrected.

Additional evaluation cases were added to test edge conditions.

## Remaining Risks

The catalog is synthetic and much smaller than the real McGill catalog.

There is no timetable conflict detection.

The system does not track graduation requirements.

The overload calculation should be validated independently from the language model output.

## Future Work

Connect to a real course catalog API.

Add timetable conflict checking.

Add degree progress tracking.

Add stronger validation for structured outputs.
