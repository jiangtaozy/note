- How to check if a canvas is blank?

      
      function isCanvasBlank(canvas) {
        const blank = document.createElement('canvas');
        blank.width = canvas.width;
        blank.height = canvas.height;

        return canvas.toDataURL() === blank.toDataURL();
      }
