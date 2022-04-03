@@ -22,7 +22,7 @@ module.exports = (req, res) => {
		rotate = 0,
        customColorList = ''    // Select only the ones you want from the set color list.   ex) "0,1,5,6"
    } = req.query;
    let color = req.query.color;
    let color = req.query.color || 'B897FF';
    let fontColor = req.query.fontColor;
    let textBgColor = '#ffffff';

@@ -48,6 +48,7 @@ module.exports = (req, res) => {
                                ${model.gradientDef(color)}
                                ${model[regexData(type)].render(reversal, checkColor(color), height)}`
                            : ``;
    console.log(svgContentScript);

    // set 'text' - The layout changes depending on whether or not 'textBg' is used.
    let textScript =    `${ textBg === 'true'
