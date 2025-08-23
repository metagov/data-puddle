# Voice to Vision

## Project Description

Voice to Vision is a sociotechnical system designed to bridge community voices and planning outputs in civic decision-making processes, with a first case study deployed in particularly neighborhood planning in New York City. The system addresses the critical gap in trust and transparency that occurs when community members send feedback "into a void" without understanding how their input influences outcomes.

Through a structured yet flexible data infrastructure and complementary interfaces for both community members and planners, Voice to Vision facilitates shared understanding across the civic ecosystem. The system comprises interconnected data collections that organize community input while maintaining adaptability for diverse engagement contexts.

## System Architecture

The Voice to Vision system operates through:

1. **Structured Data Architecture**: Interconnected collections that organize community input while maintaining flexibility for various engagement contexts
2. **Community-Facing Platform**: Makes engagement processes transparent and accessible to residents, allowing them to see themselves reflected in the process and discover patterns within feedback
3. **Sensemaking Interface**: Helps planners organize, analyze, and synthesize community feedback into actionable outputs with systematic tools that find connections across diverse inputs

## Data Structure Overview

Our flat-file structure captures the complete civic engagement ecosystem through six main collections:

- **Projects**: Core engagement initiatives with phases, timelines, and outcomes
- **Events**: Specific engagement activities with location, stakeholder, and resource information
- **Voices**: Individual community feedback with themes, codes, and connection to outputs
- **Outputs**: Planning decisions and documents that result from community input
- **Stakeholders**: Organizations and entities involved in the planning process
- **Participants**: Community members providing input (with privacy-conscious demographics)
- **SubGeographies**: Neighborhood and area definitions for spatial analysis
- **Topics**: Thematic organization including main topics, tags, and structural codes

## Research Foundation

This system was developed through an extensive iterative design process with 21 stakeholders and field evaluation involving 24 participants. Key findings reveal:

- **Planners value**: Systematic sensemaking tools that find connections across diverse inputs
- **Community members prioritize**: Seeing themselves reflected in the process, discovering patterns within feedback, observing the rigor behind decisions, and ensuring actionable outcomes

## Website and Demo

Live website of community facing platform for New York City Planning: [https://v2v-jamaicaplan.ccc-mit.org/](https://v2v-jamaicaplan.ccc-mit.org/)

## Repository and Technical Details

The system promotes shared understanding among elected officials, planners, and community members by enhancing transparency and legitimacy in civic decision-making processes. The interoperable data structure supports diverse civic engagement contexts while maintaining consistency for analysis and connection-making.

## Contact and Collaboration

For questions about implementation, research findings, or potential collaborations in civic technology and participatory design, please refer to the supplementary materials or contact the research team through the project website: Maggie Hughes at mhughes4@media.mit.edu and Cassandra Overney at coverney@media.mit.edu

## Data Format

This project exports data in a structured JSON format with the following main collections:
- Projects, Events, Voices, SubGeographies, Topics, Outputs, Stakeholders, and Participants

See `voice_to_vision_flatfile_structure.json` for the complete data schema and field definitions.
