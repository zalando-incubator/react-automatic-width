# react-automatic-width

[![Build Status](https://travis-ci.org/zalando/react-automatic-width.svg?branch=master)](https://travis-ci.org/zalando/react-automatic-width) [![Coverage Status](https://coveralls.io/repos/github/zalando/react-automatic-width/badge.svg?branch=master)](https://coveralls.io/github/zalando/react-automatic-width?branch=master)

So, you found those cool components like [fixed-data-table](https://facebook.github.io/fixed-data-table/) and [react-d3-components](https://github.com/codesuki/react-d3-components) that do whatever you want, with just one problem: They only work on fixed width! You care about responsiveness and different display sizes. You want variable width! **HULK SMASH!**

One solution: Just wrap it in `AutoWidth`, so that this:
~~~ jsx
import D3 from 'react-d3-components';

<D3.BarChart
    width={500} /> // ;_;
~~~

Can work like this: 

~~~ jsx
import D3 from 'react-d3-components';
import AutoWidth from '@zalando/react-automatic-width';

<AutoWidth>
    <D3.BarChart /> {/* ^_^ */}
</AutoWidth>
~~~

**Here, give a direct statement about the project: react-automatic-width is an [UMD](https://github.com/umdjs/umd) module that automatically sets `width` property on child components. It works out-of-the-box and accepts any property you throw at it. This way, you can use classes and media queries for the autowidth container.** 

**react-automatic-width does its job by attaching a listener to (*a*, or *the*?) `resize` event of `window`. In it, the component reads the current width of its DOM node and sets this as the `width` property on its children.**

**Some questions: Is this project like anything else out there? If not, say that. If yes: Does it do something better/different/faster/simpler? What is it like, and what is it not like (here, you want to preemptively respond to "yeah, but isn't this like ...?" questions); what is it especially good for? who is your target audience?**

**Also, briefly state:**
- dev status (is it buggy? would you trust it? etc.)
- technical requirements/what a person needs to get it up and running
- incompatibilities, if any
- what it works particularly well with/on, and not-so-well (if appropriate)

### Installation & Usage

Install react-automatic-width with:

    npm i -S @zalando/react-automatic-width

Then load it however you want:

    <AutoWidth className="responsive">
        <D3.BarChart />
    </AutoWidth>

### Contributing

This project welcomes contributions from the community. Here are some issues and areas where we could use some help:
* Uses `addEventListener`, so currently there's no IE8. PRs welcome.
* Uses `clientWidth` because that worked on our current Chrome. Might be funky in your browser. PRs welcome.
* Not clear what should happen if the window is resized while the container is not displayed. Currently zero-widths just get ignored. Drop a line via the Issues Tracker if you have some ideas.

### License

Apache 2.0
